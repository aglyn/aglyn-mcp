# Aglyn for AI assistants

Connect an AI assistant to your [Aglyn](https://aglyn.com) workspace and ask
it for things in plain words: who filled in a form this week, add these
services to a site, mark an order shipped, log a call and set a reminder.

You sign in to Aglyn, pick the workspace, and choose **View only** or **View
and make changes**. There is no key to copy, and you can disconnect at any
time in Aglyn under **Settings → API keys → Connected apps**.

**Connector address:** `https://app.aglyn.com/api/mcp`

It works with any assistant that supports the Model Context Protocol (MCP)
with sign-in. This repository packages it for the ones below.

## What the assistant can do

| Area | It can |
| --- | --- |
| Sites | List your sites, create a site, publish a site |
| Pages | List a site's pages: their names, addresses, and whether each is published |
| Search listings | See and change how a site and each of its pages appear in search results: title and short description |
| Business details | See and change the business name, slogan, phone, email, address and social links |
| Site content | Read and edit datasets and their records |
| Contacts and CRM | Find, add, update and merge contacts; companies, deals, tasks, activities, leads, email templates |
| Form submissions | Read, mark read, delete |
| Products | Add, edit and delete products, with their prices and stock; a new product starts as a draft the store does not show |
| Orders | Read; mark an order shipped or delivered with tracking |
| Bookings | Read |
| Media | List and upload |

Changes to products, search listings and business details show on the live
site as soon as they are saved. There is no draft and no publish step, so
read what the assistant proposes before you approve it.

It cannot change what is on a page or how it looks, change themes, cancel or
refund an order, move or cancel a booking, rename or delete a site, replace or
delete media, or change your team, plan or billing. Variants follow a
product's options, such as sizes and colors, so a single variant is not added
or removed on its own.

Connected before products, search listings, pages and business details were
added? Disconnect and connect again, and approve the new list, to use them.

## Install

### Claude (web, desktop, mobile)

Settings → Connectors → Add custom connector, and enter the connector address.

### Claude Code

```bash
claude plugin marketplace add aglyn/aglyn-mcp
```

```bash
claude plugin install aglyn@aglyn
```

Then run `/mcp`, choose **aglyn**, and sign in.

### Cursor

Add to `~/.cursor/mcp.json`, then sign in when Cursor asks:

```json
{ "mcpServers": { "aglyn": { "url": "https://app.aglyn.com/api/mcp" } } }
```

### Gemini CLI

```bash
gemini extensions install https://github.com/aglyn/aglyn-mcp
```

Then run `/mcp auth aglyn`.

### VS Code

```bash
code --add-mcp '{"name":"aglyn","type":"http","url":"https://app.aglyn.com/api/mcp"}'
```

### Anything else

Add a remote (Streamable HTTP) MCP server with the connector address.
Scripts with nobody to sign in can send an API key as
`Authorization: Bearer aglyn_sk_…` instead; see the
[API docs](https://docs.aglyn.com/api).

## What is in this repository

- `skills/`: plain-Markdown guidance for the assistant: `aglyn` (using the
  tools), `aglyn-console` (work done in the console through a browser),
  `aglyn-read-site` (reading a published Aglyn site as text).
- `.claude-plugin/`, `.mcp.json`: the Claude Code plugin.
- `.cursor-plugin/`, `mcp.json`: the Cursor plugin.
- `gemini-extension.json`, `GEMINI.md`: the Gemini CLI extension.

The server itself is part of Aglyn, which is open source:
[aglyn/aglyn](https://github.com/aglyn/aglyn).

## Links

[Guide](https://docs.aglyn.com/marketing-and-automation/workflows-and-actions/claude) ·
[API docs](https://docs.aglyn.com/api) ·
[Privacy](https://aglyn.com/legal/privacy) ·
[Terms](https://aglyn.com/legal/terms) ·
[Support](https://aglyn.com/contact)

Apache-2.0.
