# Local APEX environment

Copy this file to `local-apex-environment.md`. That local file is ignored by Git. Keep credentials in the saved Oracle connection configuration; do not add passwords, tokens, connection strings, wallets, or hosts here.

## Confirmed environment

- Saved Oracle connection: `<exact saved connection name>`
- Parsing schema: `<parsing schema>`
- APEX workspace: `<workspace name>`
- APEX workspace ID: `<workspace ID>`
- APEX application ID: `<application ID>`

Treat the parsing schema and APEX workspace as different identifiers. Re-query the database if an operation reports that any value is stale.

## Live validation

Run SQLcl through the connected Oracle tooling with:

`apex validate -input "<absolute-project-path>\apex-agents" -workspaceid <workspace ID>`

Resolve `<absolute-project-path>` from the current repository. Validation is check-only; never import or deploy without an explicit user request.
