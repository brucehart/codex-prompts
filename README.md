# Codex CLI Custom Prompts

This folder holds custom prompts that become slash commands in Codex CLI. Each prompt is a Markdown file with YAML frontmatter describing how it appears in the slash popup and which arguments it expects. Trigger them with `/prompts:<name>` from the composer to paste the prompt content with your supplied arguments.

## How prompts work
- File location: Codex scans top-level Markdown files in `~/.codex/prompts/`; edit or add files here.
- Metadata: `description` shows in the popup, and `argument-hint` documents expected parameters.
- Arguments: supply positional `$1–$9` or named values like `FILES=<paths>`; `$ARGUMENTS` expands all positional args. Use `$$` to render a literal `$`.
- Reloading: restart Codex (or start a new conversation) after editing prompt files so changes load.
- Pair with built-in commands: use `/status` to confirm session settings, `/diff` to review changes Codex makes, and `/undo` if you need to roll back an action.

## Prompts in this repo
- `api-doc.md` — Generate comprehensive API documentation for given files, including usage, inputs/outputs, error cases, and best practices. Arguments: `FILES=<paths>`.
- `commit.md` — Commit specified files to a branch with a detailed message; defaults to all pending changes on the current branch. Arguments: `FILES=<paths>`, `BRANCH=<branch>`.
- `explain.md` — Explain code or architecture at a chosen depth with key concepts and pitfalls. Arguments: `FILES=<paths>`, `DEPTH=<summary|full|architecture>`.
- `generate-pr.md` — Commit current changes and open a PR targeting a branch, creating a feature branch when needed. Arguments: `DEV_BRANCH=<dev_branch>`, `TARGET_BRANCH=<target_branch>`.
- `refactor.md` — Refactor files with an optional focus area while keeping behavior unchanged. Arguments: `FILES=<paths>`, `FOCUS=<cleanliness|performance|fp|readability>`.
- `tests.md` — Generate tests with edge cases and setup notes for a target path or function. Arguments: `TARGET=<path|function>`, `TYPE=<unit|integration|e2e>`.

## Example usage
```
/prompts:refactor FILES="src/app.ts" FOCUS="performance"
/prompts:tests TARGET="src/lib/api.ts" TYPE="integration"
```

Use these prompts to keep common workflows fast, repeatable, and discoverable directly from the slash command popup.
