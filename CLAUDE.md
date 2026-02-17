# verynormal.info Reading List

Curated software reading list published at verynormal.info/reading-list.

## What This Is

A single markdown file (`reading-list.md`) tracking software articles Jesse reads, organized by category. Source of truth lives here; Ghost page is updated manually by pasting rendered HTML.

## Entry Format

```markdown
- YYYY-MM-DD [Title](url) by Author — Jesse's one-liner take.
```

- Newest first within each category
- Categories are `##` headers
- Author is the person who wrote the article (not the publication)
- One-liner reflects Jesse's take, not the article's abstract
- Keep it minimal: title, link, author, date, one sentence

## Adding an Entry

When Jesse says "add this to my reading list":

1. Fetch the URL to understand the article
2. Ask Jesse for his take if not provided (or confirm your summary)
3. Determine the category — use an existing `##` header if it fits, create a new one if it doesn't
4. Prepend the entry (newest first) under the right category header
5. Commit: `git add reading-list.md && git commit -m "Add: [article title]"`

## Publishing to Ghost

Ghost Pro Starter plan — no Admin API access. Publishing is manual:

1. Render `reading-list.md` as clean HTML
2. Jesse pastes it into the Ghost page editor at `/reading-list/`

When Jesse says "publish reading list", render the full file as HTML ready to paste.

## qmd Search

qmd is installed via Node 22 (asdf). The wrapper handles version pinning:

```bash
bin/qmd search "query"        # keyword search
bin/qmd vsearch "query"       # semantic search
bin/qmd query "query"         # hybrid (best results)
bin/qmd embed                 # re-embed after adding entries
```

Run `bin/qmd embed` after adding new entries to update the vector index.

## Tech Details

- qmd requires Node 22 (not 24) — `tsx` devDependency doesn't install globally
- `bin/qmd` wrapper sets `ASDF_NODEJS_VERSION=22.14.0` and runs from qmd's package dir
- qmd collection name: `reading-list`
- Models cached at `~/.cache/qmd/models/` (~328MB embedding model)
