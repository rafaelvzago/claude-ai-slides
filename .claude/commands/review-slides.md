# /review-slides

Review the presentation slides for consistency and correctness.

## Workflow

1. Count sections in both PT-BR and EN files:
   ```
   grep -c '<section class="slide"' claude-code-open-source.html
   grep -c '<section class="slide"' claude-code-open-source-en.html
   ```
   Both must be equal.

2. Verify sections are balanced (open == close):
   ```
   grep -c '</section>' claude-code-open-source.html
   grep -c '</section>' claude-code-open-source-en.html
   ```

3. Verify `preventDefault` is intact (exactly 4 occurrences per file):
   ```
   grep -c 'preventDefault' claude-code-open-source.html
   grep -c 'preventDefault' claude-code-open-source-en.html
   ```

4. Check for unaccented Portuguese words in the PT-BR file:
   ```
   rg '\b(codigo|voce|nao|sessao|verificacao)\b' claude-code-open-source.html
   ```

5. Verify agenda goTo() indices match actual slide positions:
   - List all `<section class="slide"` with line numbers
   - Compare against goTo() values in the agenda

6. Report findings.

## Usage
```
/review-slides
```
