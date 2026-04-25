---
name: translate
description: >
  Use when PT-BR slides were updated and EN needs to be synced,
  or vice versa. Translates visible text only, preserving HTML structure.
  Triggers when the user says "translate", "sync EN", "sync PT",
  "update English version", or "atualizar versão em inglês".
---

# Translate Skill

## What to translate

- Titles (h1, h2, h3)
- Paragraphs and text content
- List items (li)
- Table cells (th, td)
- Blockquotes
- Terminal bar titles (e.g. `claude ~ /fundamentos` → `claude ~ /fundamentals`)
- Prompts (e.g. `$ claude "qual o problema..."` → `$ claude "what's the problem..."`)

## What NOT to translate

- CSS (everything inside `<style>`)
- JavaScript (everything inside `<script>`)
- HTML attributes (class, id, onclick, style, href)
- URLs and links
- Project names (QualityFlow, OSSM, Kiali, etc.)
- Command names (`/compact`, `/rewind`, `git worktree`, etc.)
- File names (CLAUDE.md, AGENTS.md, settings.json, SKILL.md)
- `preventDefault` — this is a JavaScript method, NOT a Portuguese word
- ASCII art (keep identical)
- Code inside `<code>` tags (unless it's natural language shown to the audience)

## Workflow

1. Identify which slides changed (diff the files or ask the user)
2. Find the corresponding slide in the other language file
3. Translate only the visible text content
4. Verify section count matches between both files
5. Verify `preventDefault` count is exactly 4 in both files

## Common PT-BR → EN translations

| PT-BR | EN |
|-------|-----|
| Fundamentos | Fundamentals |
| Fluxo de Desenvolvimento | Development Flow |
| Próximos Passos | Next Steps |
| Código é Barato | Code is Cheap |
| O Plano é Tudo | The Plan is Everything |
| Dicas do dia-a-dia | Day-to-day tips |
| Segurança e Guardrails | Security and Guardrails |
| Trabalhando em Paralelo | Working in Parallel |
| Do Individual ao Time | From Individual to Team |
