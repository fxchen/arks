---
updated: 2026-07-21
tags: [routine]
---

# Routine: weekly health check

**Trigger:** start of the first session each week (per AGENTS.md), or "check
the vault."

**Steps — run exactly, report before fixing anything:**

Before reporting, read `System/routines/accepted-exceptions.md` if it exists.
It is valid only with normal frontmatter and entries containing a date, file,
check number, one-line reason, "approved by <the human>," and an optional
review date. Each exception binds to one file and one check, never a blanket.
List valid accepted exceptions briefly instead of presenting them as new
problems.

1. **Records history.** Run
   `git log --name-only --diff-filter=MDR -- Records/` and
   `git status --porcelain Records/`. If there are no commits yet, report the
   history check as not applicable. Otherwise, committed M is a violation
   unless it is an accepted privacy redaction. Explain every D or R: deletion
   is legitimate only as a privacy redaction, and a rename breaks links. Use
   status to find uncommitted M entries for tracked Records. Untracked new
   Records are fine; never recommend restoring redacted sensitive material.
2. **Provenance.** Every Knowledge note needs a nonempty `sources:` YAML
   frontmatter list naming Record file slugs. Prose and inline citations are
   not alternatives.
3. **Links.** Resolve every wikilink by recursively matching its filename slug,
   excluding `System/templates/` and `.context/`. For `[[slug|Display]]`, use
   the slug before the pipe. One match is healthy, multiple matches violate,
   and zero matches form the healthy to-write queue.
4. **Frontmatter.** Check Markdown content files in exactly `Records/`,
   `Knowledge/`, `Action/`, `System/decisions/`, and `System/routines/` for
   `updated:` and `tags:` in the required forms. `updated:` must be a real
   `YYYY-MM-DD` date and `tags:` a YAML list. In `System/templates/`, check
   field presence, not values; placeholders are deliberate. Exclude
   `.context/`. The seven named exemptions are `README.md`, `AGENTS.md`,
   `CLAUDE.md`, `LICENSE`, `GLOSSARY.md`, `SPEC.md`, and `START-HERE.md`.
5. **Naming.** Check Markdown content filenames for lowercase-hyphenated names
   with no spaces. Dotfiles and non-Markdown assets are out of scope; exclude
   `.context/` and the seven named exemptions. Require a `YYYY-MM-DD-` prefix
   on every Record and every dated review file in `Action/`; Knowledge notes
   and living Action documents are not date-prefixed.

Report each check as PASS or findings in ordinary language. For each finding,
give the exact proposed change, why it matters, whether it is reversible, and
one recommendation: **Fix**, **Leave unchanged**, or **Accept as exception**.
End with the most important recommendation and ask before changing anything.
If the human accepts an exception, add a dated entry to the required file shape
above only with approval; one entry covers one file and one check.
