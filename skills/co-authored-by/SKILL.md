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
4. When the repo is silent and your product is listed, end the message with that trailer. Done when the text ends with that trailer.
5. When the repo is silent and you have no published address, use the unknown-email trailer with the GitHub login. Done when the name and the address both use that login. With no login, report the product name.
6. When you know the model id, put `Model: <id>` on the line before the agent trailer. Done when that line names the model and the agent trailer is still last.
7. Commit with the current git identity. Done when `git log -1` shows that identity as Author and `%B` matches the chosen rule, with your trailer present once.

Some products append their line during `git commit`. When the commit you just created contains the trailer twice, or the appended name is a model, amend that commit so the product line is the only agent trailer. Put the model id on the `Model:` line.

## Message

```
docs(repos): add herdr-automations fork

Model: <model id>
Co-authored-by: Grok <noreply@x.ai>
```

A blank line separates the subject or body from the trailer block. The model id is the model in this session. The agent trailer is the last line. Keep human `Co-authored-by` lines, and put the agent line after them.

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
  Pi publishes no trailer. The `pi-co-authored-by` extension also writes `Generated-By: pi` and the output of `pi --version`.

## Unknown email

```
Co-authored-by: <login> <login>@users.noreply.github.com
```

The login is the GitHub account. The name and the address both use it.
