---
name: co-authored-by
description: Co-authored-by trailer for the coding agent on a git commit. Load when writing a commit message.
---

# Co-authored-by

The human stays the commit Author. The coding agent adds its trailer so the commit records who wrote the change.

The agent is the product hosting the session. Pi running Claude uses the Pi line. Cursor uses the Cursor line.

## Steps

1. Name the product you are. Done when you have one entry below, or you know you are unlisted.
2. Read the repo's attribution rule in `AGENTS.md` or `CLAUDE.md`. Done when you have that rule, or both files are silent.
3. A repo rule replaces the table, including a rule that the message carries no agent trailer. Done when the message text matches the repo rule.
4. When the repo is silent, end the message with your entry's trailer. Done when the text ends with that trailer.
5. Commit with the current git identity. Done when `git log -1` shows that identity as Author and `%B` matches the chosen rule, with your trailer present once.

Some products append their line during `git commit`. When the commit you just created contains the trailer twice, or the appended name is a model, amend that commit so the product line is the only agent trailer.

## Message

```
docs(repos): add herdr-automations fork

Co-authored-by: Grok <grok-export@users.noreply.github.com>
```

A blank line separates the subject or body from the trailer. The trailer is the last line. Keep human `Co-authored-by` lines, and put the agent line after them.

## Trailers

Copy the line. The name is the product. `Co-authored-by` and `Co-Authored-By` are the same Git trailer; keep the spelling shown.

- **Grok Build:** `Co-authored-by: Grok <grok-export@users.noreply.github.com>`
  Grok Build publishes no trailer. This is the author it sets when it commits during GitHub export.
- **Claude Code:** `Co-Authored-By: Claude Code <noreply@anthropic.com>`
- **Codex:** `Co-authored-by: Codex <noreply@openai.com>`
- **Cursor:** `Co-authored-by: Cursor <cursoragent@cursor.com>`
- **Copilot:** `Co-authored-by: Copilot <copilot@github.com>`
- **Aider:** `Co-authored-by: aider <aider@aider.chat>`
- **Crush:** `Co-Authored-By: Crush <crush@charm.land>`
- **Command Code:** `Co-authored-by: CommandCodeBot <noreply@commandcode.ai>`
- **Pi:** `Co-Authored-By: Pi <noreply@pi.dev>`
  Pi publishes no trailer. The `pi-co-authored-by` extension also writes `Generated-By: pi` and the output of `pi --version`.

OpenCode and Gemini CLI publish no trailer. Report that product name instead of inventing an address.
