# Power tools

*As of 2026-08. Everything on this page is optional, and this page is allowed
to go stale — the method doesn't depend on any of it. Before adopting
anything here, read the engine contract in [`SPEC.md`](../SPEC.md) §5.*

## Search engines (Tier 1+, when [`02-search.md`](02-search.md) says so)

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
  If you are comfortable working from the terminal, Obsidian's
  [official CLI](https://help.obsidian.md) shipped in v1.12 (early access in
  February 2026) and has been free for all users since v1.12.4 (late February
  2026). Enable it inside the app at **Settings → General → Command line
  interface**. It drives the running desktop app, so Obsidian must be open and
  the CLI is desktop-only. It covers notes, search, tags, properties, and more
  from the terminal, giving both you and your agent a way to work against the
  vault. Some commands open or drive the app UI, which can hang an unattended
  agent session. Have your agent prefer read-only commands and test them
  interactively before adding any to a routine.

## What's deliberately absent

Databases, memory services, and sync products. They solve real problems for
software teams; for a vault, they trade away the two properties that make
ARKS durable — files that stay legible and portable.
