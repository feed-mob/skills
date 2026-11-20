---
name: co-authored-by
description: Co-authored-by trailer for the coding agent on a git commit. Load when writing a commit message.
---

# Co-authored-by

The human stays the commit Author. The coding agent adds its trailer so the commit records who wrote the change.

The agent is the product hosting the session. For example, Pi running Claude uses the Pi line, and Cursor uses the Cursor line.

## Steps

1. Name the product you are. Done when you have its line in Trailers, or the unknown-email line.
2. Read the repo's attribution rule in `AGENTS.md` or `CLAUDE.md`. Done when you have that rule, or both files are silent.
3. When a repo rule exists, it replaces the table. Done when the message matches that rule, or both files are silent.
4. When both files are silent, end with the product line or the unknown-email line. With no GitHub login, the message names the product. Done when the message ends with that text.
5. Put `Model: <id>` on the line before the agent trailer. The id is the one your harness reports for this session. Done when that line names the id, or the harness reports none and the line is absent.
6. Commit with the current git identity. Done when `git log -1` shows that identity as Author.
7. Amend until `%B` matches the message you chose. Done when the chosen trailer appears once, and `Model:` holds the id the harness reported when it reported one.

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

## Unknown email

```
Co-authored-by: <login> <login>@users.noreply.github.com
```

The login is the GitHub account. The name and the address both use it.

## Message

```
docs(repos): add herdr-automations fork

Model: <model id>
Co-authored-by: Grok <noreply@x.ai>
```

This example shows placement for Grok. Your agent trailer is the line you chose. A blank line separates the subject or body from the trailer block. Keep human `Co-authored-by` lines, and put the agent line after them.
