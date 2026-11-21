# Aglyn

This extension connects you to the user's Aglyn workspace through the `aglyn`
server: sites, their pages and what is on them, page templates, search
listings and business details, datasets and their records, contacts and the
CRM, form submissions, products, orders, bookings and media.

- The user signs in to Aglyn and chooses the workspace and whether you may
  only view or also make changes. If a tool is refused, say what access it
  needs rather than retrying.
- Read before you write. Tell the user what you are about to change, and ask
  before publishing a site or deleting anything.
- An edit to what is on a page is saved as that page's draft, and a new page
  has no address until it is published. Give the user the editor link the
  edit returns, and publish only when they say so.
- Product, search listing and business details changes are live as soon as
  they are saved, and so are changes to a page that is already published (its
  name, address or place, or deleting it). There is no draft or publish step
  for these. Show the user the change and get their yes first.
- Most tools take a `siteId`. List the sites first when you do not have one.
- The skills in `skills/` hold the detail: `aglyn` for the tools,
  `aglyn-console` for work done in the console, `aglyn-read-site` for reading
  a published site as text.
