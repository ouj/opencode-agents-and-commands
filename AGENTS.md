# AGENTS.md

This repository contains OpenCode configuration and command definitions.
It is not a traditional application source tree, so build and test guidance
focuses on validating configuration and command behavior.

## Repository Overview

- `commands/` holds OpenCode command definitions in Markdown.
- `opencode.json` is the main OpenCode configuration file.
- `README.md` documents installation and usage.
- `AGENTS.md` defines agent behavior and repo conventions.

## Build, Lint, and Test

There is no conventional build or lint pipeline in this repo.
Validation is done by OpenCode and by manual command execution.

### Configuration Validation

- OpenCode validates `opencode.json` against its schema on load.
- Keep `$schema` present and correct in `opencode.json`.

### Command Validation

- Commands in `commands/` are loaded by OpenCode automatically.
- Validate new or edited commands by running them in OpenCode.
- Prefer small, focused changes and verify behavior after edits.
- To sync repo command and agent definitions to local OpenCode config, run:
  `rsync -av --delete ./agents/ ~/.config/opencode/agents/ && rsync -av --delete ./commands/ ~/.config/opencode/commands/`

### Single Test Guidance

- There is no unit test runner in this repo today.
- To validate a single change, run the specific command in OpenCode.
- If a dedicated test runner is added later, document the exact
  single-test command here and in `README.md`.

## Code Style and Conventions

### Command Definition Files

- Use YAML frontmatter with `description`, `agent`, and `model`.
- Order frontmatter keys as: `description`, `agent`, `model`.
- Keep descriptions in present tense and sentence case.
- Keep frontmatter values short and unquoted unless necessary.
- Separate frontmatter from body with a blank line.

### Command Body Style

- Use short, imperative sentences.
- Avoid ambiguous instructions and hidden assumptions.
- Include explicit constraints when needed (for example, ask before
  staging untracked files).

### JSON Configuration Style

- Use 2-space indentation and LF line endings.
- Keep keys ordered logically: schema, core config, plugins.
- Avoid trailing commas and keep JSON valid.
- Prefer explicit `enabled` flags over implied behavior.

### Markdown Style

- Use ATX headings (`#`, `##`) and keep heading hierarchy consistent.
- Wrap shell snippets in fenced code blocks with `bash` info strings.
- Keep line length around 80-100 characters where reasonable.
- Use simple lists, one idea per line.

### Naming Conventions

- Command filenames use snake_case: `stage_and_commit.md`.
- Command names should reflect their file name and description.
- Avoid abbreviations unless widely understood.

### Imports and Dependencies

- This repo does not include code with imports.
- If you add scripts, prefer standard library imports first.
- Do not add dependencies unless they are required and documented.

### Types

- If adding Python scripts, include type hints for all functions.
- Avoid unused imports.
- Use modern typing syntax (for example, `list[str]`).

### Formatting and Linting

- There is no formatter configured.
- For Python additions, run `ruff format` before commit.
- For any new formatter, document it here and in `README.md`.

### Error Handling

- Fail fast with clear, user-facing error messages.
- Ask for confirmation before destructive operations.
- When unsure, explain assumptions and list safe next steps.

## Security and Secrets

- Do not commit real API keys, tokens, or credentials.
- Use placeholders in config files and document how to supply real values.
- Treat `opencode.json` as potentially sensitive; review before sharing.

## Git and Commit Conventions

- Use Conventional Commits for all changes.
- Examples: `feat: add command`, `docs: update README`.
- Keep the first line under 72 characters.
- Use body bullets only when the change needs extra context.
- Never push directly to `origin/main`; create a branch first.

## Documentation Expectations

- Update `README.md` when usage or installation changes.
- Keep `AGENTS.md` in sync with repo capabilities.
- Document any new commands with intent and expected outputs.

## Change Review Checklist

- Confirm `opencode.json` remains valid JSON.
- Verify command frontmatter order and required fields.
- Ensure command descriptions are present tense and sentence case.
- Run any edited command in OpenCode to validate behavior.
- Update `README.md` when behavior or usage changes.
- Check for secrets and remove any real credentials.
- Keep diffs focused on the requested change.
- Re-check schema URLs after upgrades.

## File Hygiene

- Use LF line endings.
- Avoid trailing whitespace.
- Keep a newline at end of file.
- Default to ASCII unless a file already uses Unicode.
- Do not reformat unrelated files.

## Cursor and Copilot Rules

- No `.cursor/rules/`, `.cursorrules`, or `.github/copilot-instructions.md`
  files were found in this repository.
- If such rules are added later, summarize them here.

## Operational Notes for Agents

- Do not stage untracked files without confirmation.
- Prefer minimal diffs and avoid reformatting unrelated files.
- Keep changes focused on the requested task.

## Maintenance Checklist

- Remove obsolete commands.
- Verify all commands still match their descriptions.
- Re-check `opencode.json` schema compatibility after upgrades.
- Keep documentation accurate and concise.
