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
| Pages | List a site's pages and folders: their names, addresses, and whether each is published. Add a page, blank or from a template. Rename a page, change its address, move it or delete it. Publish the pages you choose |
| What is on a page | Read a page. Change its text, pictures and links, its spacing, alignment and other styles, and add, move or remove parts of it. Saved as a draft you review in the editor before it is published |
| Templates | List the page templates a new page can start from |
| Search listings | See and change how a site and each of its pages appear in search results: title and short description |
| Business details | See and change the business name, slogan, phone, email, address and social links |
| Site content | Read and edit datasets and their records |
| Contacts and CRM | Find, add, update and merge contacts; companies, deals, tasks, activities, leads, email templates |
| Form submissions | Read, mark read, delete |
| Products | Add, edit and delete products, with their prices and stock; a new product starts as a draft the store does not show |
| Orders | Read; mark an order shipped or delivered with tracking |
| Bookings | Read |
| Media | List and upload |

Changes to what is on a page are saved as a draft, and a new page has no
address until it is published. Visitors see neither until the page is
published, by you in the editor or by the assistant when you ask it to.

Changes to products, search listings and business details show on the live
site as soon as they are saved. So do changes to a page that is already
published: its name, its address, where it sits, and deleting it. There is no
draft and no publish step for these, so read what the assistant proposes
before you approve it.

It cannot change a site's theme, its layouts, your reusable components or the
templates themselves, and it cannot redesign a whole site. On a page it cannot
set rich text with mixed formatting or pick an icon. It cannot cancel or
refund an order, move or cancel a booking, rename or delete a site, replace or
delete media, or change your team, plan or billing. Variants follow a
product's options, such as sizes and colors, so a single variant is not added
or removed on its own.

Connected before a tool you want was added? Disconnect and connect again, and
approve the new list, to use it.

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
