# Aglyn

This extension connects you to the user's Aglyn workspace through the `aglyn`
server: sites, datasets and their records, contacts and the CRM, form
submissions, orders, products, bookings and media.

- The user signs in to Aglyn and chooses the workspace and whether you may
  only view or also make changes. If a tool is refused, say what access it
  needs rather than retrying.
- Read before you write. Tell the user what you are about to change, and ask
  before publishing a site or deleting anything.
- Most tools take a `siteId`. List the sites first when you do not have one.
- The skills in `skills/` hold the detail: `aglyn` for the tools,
  `aglyn-console` for work done in the console, `aglyn-read-site` for reading
  a published site as text.
