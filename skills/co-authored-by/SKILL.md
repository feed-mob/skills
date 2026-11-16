---
name: co-authored-by
description: Co-authored-by trailer for the coding agent on a git commit. Load when writing a commit message.
---

# Co-authored-by

The human stays the commit Author. The coding agent adds its trailer so the commit records who wrote the change.

The agent is the product hosting the session. Pi running Claude uses the Pi lines. Cursor running any model uses the Cursor line.

## Steps

1. Name the product you are. Done when you have one row below, or you know you are unlisted.
2. Read the repo's attribution rule in `AGENTS.md` or `CLAUDE.md`. Done when you have that rule, or both files are silent.
3. A repo rule replaces the table, including a rule that the message carries no agent trailer. Done when the message text matches the repo rule.
4. When the repo is silent, end the message with your row's trailer. Done when the text ends with that trailer.
5. Commit with the current git identity. Done when `git log -1` shows that identity as Author and `%B` matches the chosen rule, with your trailer present once.

Some products append their line during `git commit`. When the commit you just created contains the trailer twice, amend that commit so one copy remains.

## Message

```
docs(repos): add herdr-automations fork

Co-authored-by: Grok <noreply@x.ai>
```

A blank line separates the subject or body from the trailer. The trailer is the last line. Keep human `Co-authored-by` lines, and put the agent line after them.

## Trailers

Copy the line. `Co-authored-by` and `Co-Authored-By` are the same Git trailer; keep the spelling shown.

- **Grok:** `Co-authored-by: Grok <noreply@x.ai>`
- **Claude Code:** `Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>` — replace `Opus 4.6` with the session's model display name. With no display name: `Co-Authored-By: Claude <noreply@anthropic.com>`
- **Codex:** `Co-authored-by: Codex <noreply@openai.com>`
- **Pi:** the model line, then the harness line. Replace the model name and the version (`pi --version`):

  ```
  Co-Authored-By: Claude Sonnet 4 <noreply@pi.dev>
  Generated-By: pi 1.5.2
  ```

- **Cursor:** `Co-authored-by: Cursor <cursoragent@cursor.com>`
- **Crush:** `Co-Authored-By: Crush <crush@charm.land>`
- **Command Code:** `Co-authored-by: CommandCodeBot <noreply@commandcode.ai>`

An unlisted agent uses the trailer its product publishes. Report the product name when it publishes no address.
