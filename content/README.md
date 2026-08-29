# content/

Git-tier content: entries of collections with `storage: "git"`
(`content/<collection>/<slug>.json`) and plugin data declared git-backed
(`content/<pluginId>/<collection>/<id>.json`, e.g. form definitions).

Saving in the admin commits here; editing a file here is picked up on the
next read. The static build renders these files directly. Frequently edited
or sensitive data stays in the database, and test data lives in `seed/`.

## Agent context

`.agents/skills/` holds skills the issue agent loads on every run, and
`.mcp.json` lists extra MCP servers the agent may use.
