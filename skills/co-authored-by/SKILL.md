---
name: co-authored-by
description: Co-authored-by trailer for the coding agent on a git commit. Load when writing a commit message.
---

# Co-authored-by

The human stays the commit Author. The coding agent adds its trailer so the commit records who wrote the change.

The agent is the product hosting the session. Pi running Claude uses the Pi line. Cursor uses the Cursor line.

## Steps

1. Name the product you are. Done when you have its trailer below, or you will use the unknown-email line.
2. Read the repo's attribution rule in `AGENTS.md` or `CLAUDE.md`. Done when you have that rule, or both files are silent.
3. A repo rule replaces the table. Done when the message text matches the repo rule.
4. When the repo is silent, end the message with that product's trailer, or with the unknown-email line. With no GitHub login, the message names the product. Done when the message ends with that text.
5. When you know the model id, put `Model: <id>` on the line before the agent trailer. Done when that line names the model, or you have no model id and the line is absent.
6. Commit with the current git identity. Done when `git log -1` shows that identity as Author and `%B` matches the chosen rule, with the agent trailer present once.
7. When the commit you just created repeats the agent trailer, or the appended co-author name is a model, amend that commit so one product line remains and the model id is on the `Model:` line. Done when `%B` has one agent trailer.

## Message

```
docs(repos): add herdr-automations fork

Model: <model id>
Co-authored-by: Grok <noreply@x.ai>
```

The example shows placement for Grok. The agent trailer is your product's line. The model id is the model in this session. A blank line separates the subject or body from the trailer block. Keep human `Co-authored-by` lines, and put the agent line after them.

## Trailers

Copy the line. The name is the product. `Co-authored-by` and `Co-Authored-By` are the same Git trailer; keep the spelling shown.

- **Grok Build:** `Co-authored-by: Grok <noreply@x.ai>`
- **Claude Code:** `Co-Authored-By: Claude <noreply@anthropic.com>`
  Claude Code writes this email on the commit trailer. GitHub links it to the account `claude`, whose name is Claude.
- **Codex:** `Co-authored-by: Codex <noreply@openai.com>`
- **Cursor:** `Co-authored-by: Cursor <cursoragent@cursor.com>`
- **Copilot:** `Co-authored-by: Copilot <copilot@github.com>`
- **Aider:** `Co-authored-by: aider <aider@aider.chat>`
- **Crush:** `Co-Authored-By: Crush <crush@charm.land>`
- **Command Code:** `Co-authored-by: CommandCodeBot <noreply@commandcode.ai>`
- **Pi:** `Co-Authored-By: Pi <noreply@pi.dev>`
  The `pi-co-authored-by` extension writes this line, then `Generated-By: pi` and the output of `pi --version`.

## Unknown email

```
Co-authored-by: <login> <login>@users.noreply.github.com
```

The login is the GitHub account. The name and the address both use it.
