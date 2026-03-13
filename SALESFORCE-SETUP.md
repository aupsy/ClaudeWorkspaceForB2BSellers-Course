# CRM Setup Guide

How to connect your CRM to this workspace. Each seller does this once on their own machine. Credentials are stored locally and never committed to git — your CRM data stays yours, and your org's sharing rules are always respected.

---

## How It Works

This workspace uses an **MCP (Model Context Protocol) server** to query your CRM live during Claude sessions. When you run `/call-prep Acme Corp`, Claude queries your CRM as *you* — so you only see accounts and opportunities you already have access to in your CRM. No data is synced, stored in the repo, or visible to other sellers.

```
You → Claude → MCP Server → CRM API (as you) → live data back to Claude
```

---

## Salesforce Setup (~15 minutes)

### Prerequisites
- Python 3.10+ installed (`python --version`)
- `uv` package manager installed (`pip install uv` or see uv.astral.sh)
- A Salesforce account with API access enabled

### Step 1 — Install the MCP server

```bash
uv tool install mcp-server-salesforce
```

### Step 2 — Get your Security Token

Your Salesforce security token is required for API authentication.

1. Log into Salesforce
2. Click your avatar (top right) → **Settings**
3. In the left sidebar: **Personal** → **Reset My Security Token**
4. Click **Reset Security Token** — Salesforce will email it to you
5. Save it somewhere safe

> If your org uses IP allowlisting, you may not need a security token — ask your Salesforce admin.

### Step 3 — Configure your credentials

Copy `.env.example` to `.env` in the workspace root:

```bash
cp .env.example .env
```

Edit `.env` and fill in your values:

```
SALESFORCE_USERNAME=your.email@company.com
SALESFORCE_PASSWORD=yourSalesforcePassword
SALESFORCE_SECURITY_TOKEN=theTokenFromYourEmail
SALESFORCE_INSTANCE_URL=https://yourcompany.my.salesforce.com
```

**Finding your instance URL**: It's the URL in your browser when you're logged into Salesforce (e.g., `https://acme.my.salesforce.com`).

### Step 4 — Verify the connection

Open Claude Code in this workspace and ask:

> "Query Salesforce for my open opportunities"

If you see your pipeline, you're connected. If you get an auth error, double-check your security token — it resets every time you change your Salesforce password.

### Step 5 — Update CLAUDE.md

Open `CLAUDE.md` and set the CRM field:

```
CRM: Salesforce
```

---

## HubSpot Setup (~10 minutes)

### Step 1 — Create a Private App token

1. In HubSpot: **Settings** → **Integrations** → **Private Apps**
2. Click **Create a private app**
3. Name it (e.g., "Claude Workspace")
4. Under **Scopes**, select:
   - `crm.objects.contacts.read`
   - `crm.objects.deals.read`
   - `crm.objects.companies.read`
   - `crm.objects.notes.read`
   - `crm.objects.tasks.read`
5. Click **Create app** → copy the access token

### Step 2 — Update `.mcp.json`

Replace the `salesforce` block (or add alongside it) in `.mcp.json`:

```json
{
  "mcpServers": {
    "hubspot": {
      "command": "uvx",
      "args": ["mcp-server-hubspot"],
      "env": {
        "HUBSPOT_ACCESS_TOKEN": "${HUBSPOT_ACCESS_TOKEN}"
      }
    }
  }
}
```

### Step 3 — Configure your credentials

In your `.env`:

```
HUBSPOT_ACCESS_TOKEN=pat-na1-xxxxxxxxxxxx
```

### Step 4 — Update CLAUDE.md

```
CRM: HubSpot
```

---

## Microsoft Dynamics 365 Setup (~20 minutes)

Requires an Azure AD App Registration. Ask your IT admin if you don't have permissions to create one.

### Step 1 — Register an Azure AD app

1. Go to [portal.azure.com](https://portal.azure.com) → **Azure Active Directory** → **App registrations**
2. Click **New registration** → name it "Claude Sales Workspace"
3. Set redirect URI to `http://localhost` (type: Web)
4. After creation, note your **Application (client) ID** and **Directory (tenant) ID**
5. Go to **Certificates & secrets** → **New client secret** → copy the value immediately

### Step 2 — Grant API permissions

In your app registration → **API permissions**:
- Add **Dynamics CRM** → `user_impersonation`
- Click **Grant admin consent**

### Step 3 — Update `.mcp.json`

```json
{
  "mcpServers": {
    "dynamics": {
      "command": "uvx",
      "args": ["mcp-server-dynamics"],
      "env": {
        "DYNAMICS_TENANT_ID": "${DYNAMICS_TENANT_ID}",
        "DYNAMICS_CLIENT_ID": "${DYNAMICS_CLIENT_ID}",
        "DYNAMICS_CLIENT_SECRET": "${DYNAMICS_CLIENT_SECRET}",
        "DYNAMICS_INSTANCE_URL": "${DYNAMICS_INSTANCE_URL}"
      }
    }
  }
}
```

### Step 4 — Configure your credentials

In your `.env`:

```
DYNAMICS_TENANT_ID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
DYNAMICS_CLIENT_ID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
DYNAMICS_CLIENT_SECRET=your_secret_value
DYNAMICS_INSTANCE_URL=https://yourorg.crm.dynamics.com
```

### Step 5 — Update CLAUDE.md

```
CRM: Microsoft Dynamics 365
```

---

## Seismic Setup (~5 minutes)

Used by the `/hydrate seismic` command to pull pitch decks, battle cards, and playbooks from your Seismic library into the Knowledge/ base.

### Step 1 — Get your API token

1. Log into Seismic
2. Click your avatar (top right) → **Settings** → **Integrations** → **API Access**
3. Generate a new token (or use an existing personal access token)
4. Copy the token value

> If you don't see API Access in settings, ask your Seismic admin to enable API access for your account.

### Step 2 — Find your tenant URL

Your Seismic tenant URL is the domain you use to log in — e.g., `yourcompany.seismic.com`. Do not include `https://`.

### Step 3 — Configure your credentials

In your `.env`:

```
SEISMIC_TENANT=yourcompany.seismic.com
SEISMIC_TOKEN=your_bearer_token
```

### Step 4 — Find the folder path to hydrate from

In Seismic, navigate to the folder containing your pitch decks / battle cards. The folder path is the breadcrumb trail at the top of the page, e.g., `Enterprise Sales/Pitch Decks` or `Competitive/Battle Cards`.

### Step 5 — Run hydration

```
/hydrate seismic "Enterprise Sales/Pitch Decks"
/hydrate seismic "Competitive/Battle Cards"
```

Run multiple times for different folders. Each run adds to (not overwrites) what's already in Knowledge/.

---

## Troubleshooting

**"Authentication failed" (Salesforce)**
- Your security token resets every time you change your password. Get a new one via Settings → Reset My Security Token.
- Check that `SALESFORCE_INSTANCE_URL` ends with `.salesforce.com` and has no trailing slash.

**"No data returned" (any CRM)**
- Confirm your CRM user has API access enabled (ask your admin).
- Confirm the MCP server is installed: run `uvx mcp-server-salesforce --version`.

**"MCP server not found"**
- Make sure `uv` is installed and on your PATH: `uv --version`.
- Re-run `uv tool install mcp-server-salesforce`.

**"I can see other sellers' data"**
- This should not happen — the MCP server authenticates as you, so your org's sharing rules apply. If you're seeing records you shouldn't, contact your CRM admin — it indicates a sharing model issue in the CRM itself, not in this workspace.
