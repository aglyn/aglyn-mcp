# Aglyn

This extension connects you to the user's Aglyn workspace through the `aglyn`
server: sites, their pages list, search listings and business details,
datasets and their records, contacts and the CRM, form submissions, products,
orders, bookings and media. No tool reads or edits what is on a page.

- The user signs in to Aglyn and chooses the workspace and whether you may
  only view or also make changes. If a tool is refused, say what access it
  needs rather than retrying.
- Read before you write. Tell the user what you are about to change, and ask
  before publishing a site or deleting anything.
- Product, search listing and business details changes are live as soon as
  they are saved, with no draft or publish step. Show the user the change and
  get their yes first.
- Most tools take a `siteId`. List the sites first when you do not have one.
- The skills in `skills/` hold the detail: `aglyn` for the tools,
  `aglyn-console` for work done in the console, `aglyn-read-site` for reading
  a published site as text.
