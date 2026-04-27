---
name: update-readme
description: >
  Update the README.md repository structure tree to match the current
  filesystem. Preserves existing descriptions and generates new ones
  for added files. Triggers when the user says "update readme",
  "sync readme", "update docs", "atualizar readme", or "update structure".
---

# Update README Skill

## Workflow

1. **Scan the filesystem** — get the current file tree:
   ```
   find . -not -path './.git/*' -not -name '.git' | sort
   ```
   Note every file and directory that exists.

2. **Read the current README** — use the Read tool on `README.md`.
   Extract the tree block inside the ` ``` ` fences under
   `## Repository structure`. Parse each line to build a map of
   `filepath → description` from the inline `# comments`.

3. **Compare tree vs filesystem** — identify:
   - **Added**: files/directories on disk but not in the tree
   - **Removed**: entries in the tree that no longer exist on disk
   - **Unchanged**: entries present in both

   If nothing changed, report "README is already in sync" and stop.

4. **Preserve existing descriptions** — for unchanged entries, reuse
   the exact inline `# comment` from the current tree.

5. **Generate descriptions for new entries** — for each added file:
   - Read the first 10 lines (or YAML frontmatter) to understand purpose
   - Write a short inline comment matching the existing style
   - For SKILL.md files: use the `description` from frontmatter
   - For command .md files: use the heading text
   - If purpose is unclear, ask the user

6. **Rebuild the tree** — regenerate the full tree block following
   these rules:

   **Entry order** (top to bottom):
   1. Root metadata: CLAUDE.md, AGENTS.md, CONTRIBUTING.md, README.md
   2. HTML files: index.html, slide files
   3. `docs/` directory and children
   4. `.claude/` directory: settings.json, then commands/, then skills/
   5. Commands sorted alphabetically
   6. Skills sorted alphabetically (each with SKILL.md child)
   7. CNAME and LICENSE last

   **Format**:
   - Root: `claude-ai-slides/`
   - Use `├──` for all entries except the last, which uses `└──`
   - Nested entries use `│   ` for continuation or `    ` after last
   - Align all `#` comments to the same column (pad with spaces)
   - Each description is a short phrase (no period, under ~50 chars)

7. **Replace the tree in README** — use the Edit tool to swap the old
   tree block (everything between the ` ``` ` fences under
   `## Repository structure`) with the rebuilt tree.

8. **Verify** — read back README.md and confirm:
   - The tree is inside a valid markdown code fence
   - Every file listed actually exists on disk
   - No file on disk is missing from the tree (except exclusions)
   - The `# comment` alignment is consistent

## Exclusions

Never include these in the tree:
- `.git/` and its contents
- `.claude/settings.local.json` (user-local, not committed)
- Any `memory/` directories
- `node_modules/`, `__pycache__/`, `.DS_Store`
- Plan files (`.claude/plans/`)

## Rules

- NEVER modify content outside the `## Repository structure` code fence
- NEVER modify CNAME or LICENSE files
- Preserve the exact comment style: filename padded to column, then `# description`
- Keep the surrounding README text (sections, headers, links) untouched
- If a file exists but has no obvious purpose, ask the user for a description
- When a skill or command is added, include both the directory and its SKILL.md
- Sort commands and skills alphabetically within their directories
