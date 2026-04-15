# Changelog Pipeline (managed by `/changelog` Claude Code skill)

This directory is **NOT** rendered by Mintlify. It is git-tracked so the
weekly-email source of truth is reviewable in diffs, but it is deliberately
absent from `docs.json` so nothing here surfaces on `docs.mascot.bot`.

## Files

- **`weekly-buffer.md`** — the in-flight email. Every time work ships, the
  `/changelog` command appends a new entry block here. The next
  `/changelog-send` picks up everything in this file, sends it as a single
  Resend broadcast, then rolls the file over to `sent/<ISO-week>.md` and
  resets it.
- **`sent/`** — archive, one file per ISO week (e.g. `2026-W16.md`). These
  are the exact Markdown payloads that went out; keep them for audit and
  "what did we say back then" lookups.

## Entry format contract

Each entry in `weekly-buffer.md` is framed by HTML comments so the parser
(`packages/email/buffer-parser.ts` in mascotbot-app) can extract it
unambiguously:

```md
<!-- entry:2026-04-15 tag:feature -->
## Short punchy title

Plain-Markdown body. Bullets, links, code — yes. MDX components — no.

- bullet one
- bullet two

<!-- /entry -->
```

- `entry:YYYY-MM-DD` — ship date, ISO.
- `tag:` — one of `feature`, `improvement`, `fix`, `breaking`.
- Title is the first `## ...` heading; body is everything after it up to
  `<!-- /entry -->`.

## Do NOT

- Hand-edit this file to add entries — use `/changelog` so the Mintlify
  `changelog.mdx` and this buffer stay in sync.
- Add this directory to `docs.json` — it would leak draft copy publicly.
- Delete `sent/` entries. They are the audit trail.
