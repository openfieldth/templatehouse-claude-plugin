---
name: templatehouse
description: Use when the user wants to browse, create, validate, or edit TemplateHouse projects, pages, web blocks, or shared design tokens through their connected TemplateHouse account.
---

# TemplateHouse

Use the bundled TemplateHouse MCP connector for the user's requested work.
Match the tools by their actual names and schemas in the current session; a
host may prefix their names with the plugin or connector namespace.

## Connect and inspect

- If the tools are unavailable, explain that the user must open this plugin's
  Connectors tab and add or connect TemplateHouse, then complete its OAuth sign-in.
  In Claude Code, use the `/mcp` connection interface instead. Never ask the user
  to paste passwords or access tokens into chat or package files.
- If authentication expires, use the host's connection flow and retry the
  requested operation after the user completes sign-in.
- Resolve project names with `list_projects`, pages with `list_pages`, and blocks
  with `list_blocks` or `get_block`. Use returned identifiers; do not guess them.
- For inspection requests, use read tools without creating or changing content.

## Create or edit content

1. Read `read_temha_rules` before authoring blocks. Read the relevant additional
   topics for the task, such as header-footer, forms, or swiper, using the
   current tool schema and server-provided topic names.
2. Fetch the current block before editing. Preserve fields the user did not ask
   to change, and use `update_block` for an existing block.
3. Follow the server's common-header/footer routing. When an area uses the common
   source, use the returned canonical block identifier and respect `source` and
   `writeTarget`; do not edit page copies or toggle application flags as a workaround.
4. Use `validate_block` to check a candidate without saving when appropriate.
   Validation alone does not mean the content has been saved.
5. Inspect the actual save result. Report `saved`, `verified`, and
   `verifiedScope` accurately. A server readback is not browser verification,
   and saving a project is not publishing the website.
6. If a save fails, explain the returned error and do not claim the change was
   applied. Read back the block if the result leaves the saved state uncertain.

Use the available TemplateHouse CSS tools for shared design tokens and the
image/video search tools for supported media tasks. Keep actions within the
user's request. Do not invoke destructive tools to test a connection.
