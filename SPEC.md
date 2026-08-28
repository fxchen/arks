# The ARKS Specification

**Version 0.1 · 2026-08 · status: draft**

ARKS — **A**ction · **R**ecords · **K**nowledge · **S**ystem; an AI-Ready
Knowledge System — is a method for keeping knowledge in plain files so that
both a person and an AI agent can work on it for years without it rotting.

This document states the method precisely. Everything else in this repository
is explanation, example, or convenience. A vault that follows this page is an
ARKS vault, whatever tools sit around it.

## 1. The layers

Four top-level directories, split by **revision rule** — not by topic.

| Layer | Holds | Revision rule |
|---|---|---|
| `Records/` | Raw source material: meeting notes, transcripts, captures, things you were sent | **Write-once.** A Record is filed once and never rewritten. Corrections are new Records; together, the files form an append-only collection |
| `Knowledge/` | Synthesized understanding: people, concepts, organizations | **Overwritable.** Rewritten in place as understanding improves; always cites the Records it came from |
| `Action/` | Your working surface: projects — each with exactly one living document — plus, when you need them, areas (ongoing responsibilities) and dated reviews | **Current.** Living documents are updated in place; dated reviews accumulate |
| `System/` | Infrastructure: templates, decisions, routines, maps | **Durable.** Changes rarely, and deliberately |

`System` is singular. Subfolders are whatever your content justifies — the
spec constrains the four layers and their rules, not the tree beneath them.
Layer directories may materialize when their first file arrives; an empty
layer need not exist on disk, because git does not track empty directories.

**Flow.** Information moves in one direction:
`Records → (synthesize) → Knowledge → (inform) → Action`. Never the reverse.
`System/` sits underneath all three. The root instructions file sits on top.

## 2. The invariants

Five rules. A vault that breaks them is drifting, whatever its folders say.
This document is the method's external standard; invariant 4 governs where
rules live inside a vault.

1. **`Records/` is an append-only collection.** Under normal operation, every
   Record is write-once: once filed, its content is never modified. Corrections
   are new Records. The privacy exception in §2.1 outranks this rule.
2. **Knowledge cites Records.** Every Knowledge note names its sources (a
   required `sources:` frontmatter field). A conclusion you can't trace is a
   rumor.
3. **A root `AGENTS.md` is read every session.** One tool-agnostic file at
   the vault root carries identity, structure, conventions, and permissions.
   (A one-line `CLAUDE.md` loader may import it for tools that expect that
   name.) This is what turns a folder of markdown into an operating system.
4. **One home per rule.** Every normative rule has exactly one home —
   `AGENTS.md` if it is needed every session, a file under `System/`
   otherwise. Templates and examples may restate a rule to teach it, but
   restatements defer to the home: if they ever disagree, the home wins, and
   two homes that disagree is the defect.
5. **Synthesis is a loop with one hard checkpoint.** Capture → synthesize →
   act, repeatedly. The checkpoint: the agent shows what it intends to write
   to Knowledge *before* writing it. Records may be filed freely; Knowledge
   is written with the human in the loop.

### 2.1 The exception that outranks the rule

**Privacy overrides write-once.** Records are write-once under normal
operation, but removing sensitive, dangerous, or legally removable material
is always allowed and takes precedence over every rule in this spec.

When you redact, note that a redaction happened: leave a one-line tombstone in
the Record, or file a new Record that notes it. Deleting material from the
working tree does **not** delete it from git history or existing clones. A
pasted secret must be rotated or revoked, not merely removed. Scrubbing git
history is a separate, deliberate operation. The health check must treat a
deliberate redaction as an accepted exception, not a write-once violation.

## 3. The conventions

Not aesthetics — these are what let an agent find the right file six months
later without being pointed at it.

- **Named-file exceptions.** `README.md`, `AGENTS.md`, `CLAUDE.md`, `LICENSE`,
  `GLOSSARY.md`, `SPEC.md`, and `START-HERE.md` are instruction or front-door
  files, not content. They are exempt from the lowercase-hyphenated filename
  rule and from frontmatter requirements.
- **Filenames.** Markdown content filenames are lowercase, hyphenated, and
  contain no spaces: `pricing-model.md`. Dotfiles such as `.gitignore` and
  non-Markdown assets are exempt.
- **Date prefixes.** Every Record and every dated review file in `Action/`
  begins `YYYY-MM-DD-`, as in `YYYY-MM-DD-what-it-is.md`. Knowledge notes and
  living Action documents are not date-prefixed; their slugs are timeless.
- **Frontmatter.** It is required on content files: everything under
  `Records/`, `Knowledge/`, and `Action/`, plus everything under
  `System/decisions/`, `System/routines/`, and `System/templates/`. Start with
  this schema:

  | Field | Form | Rule |
  |---|---|---|
  | `updated:` | `YYYY-MM-DD` | Required real date. On a Record, this is its capture date and never changes after filing; outside Records, it is the date of last substantive revision |
  | `tags:` | YAML list | Required |
  | `sources:` | YAML list of `Records/` file slugs | Required on Knowledge notes |
  | `source:` | Single free-text string | Optional on Records; says where the material came from, such as `phone call` |

  `sources:` plural is the provenance list on Knowledge; `source:` singular
  is the origin note on a Record. Other fields, such as `type:` or entity
  details, are optional. Files in `System/templates/` carry placeholder values
  by design; conformance checks validate that their required fields are
  present, not that placeholder values are real.
- **Wikilinks.** Every person and concept is written as `[[jordan-at-acme]]`
  on first mention — linked by filename slug, so connections build
  themselves. Resolution recursively matches that slug against Markdown
  filename slugs (the filename without `.md`) across the vault, excluding
  `System/templates/` and `.context/`. Exactly one match is resolved; multiple
  matches are ambiguous, which is a violation; zero matches form a healthy
  queue of what to write next. Alias syntax such as
  `[[jordan-at-acme|Jordan]]` resolves by the slug before the pipe. Do not
  suppress a link because its target does not exist yet.
- **The private layer.** `.context/` is gitignored: `me.md` (who the vault's
  person is, for the agent's benefit) and scratch space. `System/` is durable
  shared infrastructure; `.context/` is private per-person state.

## 4. Growing up: graduation triggers

Start with less than you think you need. Add each structure only when its
trigger fires — never before.

A vault built by the interview may legitimately start with the templates and
routines that the interview justified. These triggers govern additions after
that starting point.

| Add | When |
|---|---|
| A `changelog.md` beside a Knowledge note | You've meaningfully rewritten the same note three or more times and want the history legible without git archaeology |
| A project `index.md` with explicit archive criteria | An effort has outlived two or more sessions and accumulated more than one file |
| Per-area map files | The root README's map section no longer fits on one screen |
| Templates for a content type | You've created the third file of that type by hand |
| A routine (a saved instruction for a repeated job) | You've asked the agent to do the same multi-step job twice |

## 5. The engine contract (compatibility principles)

ARKS needs no tools. When a vault grows past what naming conventions and your
agent's own search can serve, a search or capture engine may sit underneath —
if it honors these principles. They are principles a tool must honor, not a
formal API; a formal versioned contract can come later.

1. It is **read-only over authored Markdown** — it never rewrites a note.
2. Capture features add **only dated, write-once Records**, preserving
   `Records/` as an append-only collection.
3. Its **index is disposable** — deleting it loses nothing; the files remain
   the single source of truth.
4. It **never manufactures relationships** — links are authored by people and
   agents, not inferred into the files.
5. It **excludes `AGENTS.md`** and other instruction files from its index —
   they are policy, not knowledge.
6. It **does not transmit vault content to remote services** without the
   human's explicit knowledge and consent.

Any tool meeting the contract can be adopted, swapped, or abandoned without
touching a single note. Current known-good options: `docs/power-tools.md`.

## 6. Conformance checks

A vault can be audited mechanically. `prompts/health-check.md` phrases these
as paste-ready instructions to your agent (the reference vault keeps its own
copy at `template/System/routines/health-check.md`); any tool may implement
them against this list. These checks test
the rules housed in §§2–3; they do not create another home for them. A layer
that has not yet materialized has no files to check.

Accepted exceptions live at `System/routines/accepted-exceptions.md`, which
must have normal frontmatter. Every entry contains a date, file, check number,
one-line reason, "approved by <the human>," and optionally a review date. An
exception binds to one file and one check; it can never be a blanket.

1. **Write-once Records:** run
   `git log --name-only --diff-filter=MDR -- Records/`. If the repository has
   no commits yet, report this history check as not applicable. Otherwise, M
   is a violation unless it is an accepted privacy redaction. Every D or R
   must be explained: deletion is legitimate only as a privacy redaction, and
   a rename breaks links. Also run `git status --porcelain Records/` for
   uncommitted M entries on tracked Records. Untracked new Records are fine.
2. **Provenance:** every Knowledge note has a nonempty `sources:` YAML
   frontmatter list naming `Records/` file slugs. Prose and inline citations
   are not alternatives.
3. **Links:** resolve each `[[wikilink]]` by recursively matching its slug
   against Markdown filename slugs across the vault, excluding
   `System/templates/` and `.context/`. One match resolves, multiple matches
   violate, and zero matches are reported as a healthy queue. For
   `[[slug|Display Text]]`, match `slug`.
4. **Frontmatter:** check Markdown content files in exactly `Records/`,
   `Knowledge/`, `Action/`, `System/decisions/`, and `System/routines/` for
   `updated:` and `tags:` in the forms §3 defines; `updated:` must be a real
   `YYYY-MM-DD` date. In `System/templates/`, check required field presence,
   not placeholder values. Exclude `.context/`. The seven named instruction
   and front-door files in §3 are exempt.
5. **Naming and dates:** every Markdown content filename is
   lowercase-hyphenated and contains no spaces. Dotfiles and non-Markdown
   assets are out of scope; exclude `.context/` and the seven named files in
   §3. Every Record and every dated review file in `Action/` has a
   `YYYY-MM-DD-` prefix; Knowledge notes and living Action documents do not.

A clean check is necessary, not sufficient. It cannot verify that `AGENTS.md`
was actually loaded, that citations genuinely support the claims built on
them, or that required human approvals happened. Run the check weekly; the
reference `AGENTS.md` in `template/` already asks your agent to do so.

---

*This spec is versioned prose, not software. It changes rarely and by
deliberate revision. MIT-licensed: fork it, adapt it, argue with it.*
