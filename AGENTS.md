# APEX Agent Demo

## Project layout

- Treat `apex-agents` as the APEXlang application source root.
- Store AI Agent shared components in `apex-agents/shared-components/ai-agents`.
- Follow the `oracle-apex-ai-agent` and `apexlang` skills when creating, editing, reviewing, or validating an AI Agent.

## Local APEX environment

- Before live database discovery, validation, import, or deployment, read `.codex/local-apex-environment.md` if it exists.
- That file holds local, environment-identifying values such as the saved connection name, parsing schema, APEX workspace, workspace ID, and application ID.
- It is intentionally ignored by Git. Never add it to a commit, copy it into source files, or display its values unless the task requires them.
- If the file is absent, list the available saved connections and ask for the environment values required by the task. Do not guess them.

## Database access workflow

1. Prefer the Oracle Database MCP tools over guessing a local SQLcl executable or connection string.
2. List saved connections and select the exact name specified by local environment instructions. Do not reconstruct credentials or connection details.
3. Connect and immediately inspect the active connection and schema.
4. Confirm that the active schema matches the local environment instructions before querying project objects.
5. Discover tables, views, columns, and APEX metadata from the live database before generating SQL that depends on them.
6. Use bind variables for user-controlled values and avoid `select *` in generated agent tools.
7. Disconnect when database work is finished.

Never write passwords, tokens, wallets, or other connection secrets into this repository, an APEXlang file, a skill, logs, or user-facing output.

## Validation and deployment

- Run the APEXlang compiler-truth checks required by the `apexlang` skill.
- For a live project validation, run SQLcl through the connected Oracle tooling using the workspace ID in the local environment instructions.
- Resolve the absolute project path from the current repository; do not hard-code a machine-specific path in generated source files.
- Validation is check-only. Do not import or deploy an application or shared component unless the user explicitly requests it.
