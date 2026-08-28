# Power tools

*As of 2026-08. Everything on this page is optional, and this page is allowed
to go stale — the method doesn't depend on any of it. Before adopting
anything here, read the engine contract in [`SPEC.md`](../SPEC.md) §5.*

## Search engines (Tier 1+, when [`search.md`](search.md) says so)

- **kb** ([github.com/hraness/kb](https://github.com/hraness/kb), MIT) — a
  knowledge-base CLI whose philosophy closely matches ARKS: Markdown and git
  stay authoritative, indexes are disposable. Its read and search commands
  worked against an ARKS tree via `--root` when tested against v0.17
  (2026-08).
  Notes for ARKS use: skip `kb init` (this template replaces it), set
  `kb_catalog: authored` so it writes nothing, and point capture output into
  `Records/`. Honest caveats: young project, single maintainer, requires the
  Bun runtime — have your agent do the install.
- **qmd** ([github.com/tobi/qmd](https://github.com/tobi/qmd)) — local
  hybrid search (keyword + semantic) over Markdown; the engine kb uses under
  the hood. Leaner, lower-level; needs Node or Bun and downloads local models
  (about 2 GB).

## Reading and writing

- **Obsidian** — a pleasant editor that sits directly on top of the same
  folder; renders your `[[wikilinks]]` as a clickable graph. Not either/or
  with anything here: the agent works the files, Obsidian displays them.

## What's deliberately absent

Databases, memory services, and sync products. They solve real problems for
software teams; for a vault, they trade away the two properties that make
ARKS durable — files that stay legible and portable.
