# verynormal

A personal repository for tracking reading lists and notes.

## Structure

- `reading-list.md` — Main reading list
- `monthly/` — Monthly reading notes and summaries (e.g., `202602.md` for February 2026)
- `CLAUDE.md` — Instructions for Claude (Anthropic's AI assistant)

## Monthly Link Logging

When you text Zo a URL (with or without notes), it will:

1. Fetch the page title
2. Add the entry to the current month's file in `monthly/` (format: `YYYYMM.md`)
3. Create new month files as needed
4. Commit and push to remote

Entry format:
```markdown
- [Page Title](https://link.com) — Your notes rewritten in full sentences with proper capitalization, grammar, and spelling.
```

The main `reading-list.md` is NOT updated unless explicitly requested.

## Notes

This repo is synced from GitHub: https://github.com/jesse-spevack/verynormal
