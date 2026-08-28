# Vault health check

Paste this into your agent inside your vault. This self-contained weekly check
uses real commands and clear rules to catch drift early.

The block below is written for the agent; you can stop reading here and paste
it whole.

```text
Audit this vault using the five checks below. Run each check as written, then
report. Do not fix or edit anything until I approve the exact change.

Before reporting, read System/routines/accepted-exceptions.md if it exists.
It is valid only if it has normal frontmatter and each entry gives a date, a
file, a check number, a one-line reason, and "approved by <the human>," with an
optional review date. An exception binds to one file and one check; it is never
a blanket. Do not present a valid accepted exception as a new problem; list it
briefly as already accepted instead.

1. WRITE-ONCE RECORDS. Run both commands:
     git log --name-only --diff-filter=MDR -- Records/
     git status --porcelain Records/
   If the repository has no commits yet, report the history command as not
   applicable. Otherwise, in committed history, M is a violation unless it is
   an accepted privacy redaction. Explain every D or R: deletion is legitimate
   only as a privacy redaction, and a rename breaks links. Use the status
   command to find uncommitted M entries for already tracked Records. Untracked
   new Records are fine. Never recommend restoring sensitive material removed
   by a privacy redaction.

2. PROVENANCE. Every Knowledge note must have a nonempty sources: YAML
   frontmatter list naming Records/ file slugs. A prose or inline citation is
   not an alternative. List every Knowledge note without that required list.

3. LINKS. Collect every [[wikilink]] in the vault, excluding System/templates/
   and .context/. Resolve each link by recursively matching the filename slug;
   for [[slug|Display]], use the slug before the pipe. Report three lists:
   - AMBIGUOUS — links that resolve to more than one file. This is a violation.
   - QUEUE — links that resolve to no file. This is not an error; it is a useful
     list of what the vault may need next.
   - OK — links that resolve to exactly one file. Include the count.

4. FRONTMATTER. Check Markdown content files in exactly Records/, Knowledge/,
   Action/, System/decisions/, and System/routines/ for updated: and tags:
   frontmatter in the required forms. updated: must be a real YYYY-MM-DD date,
   and tags: must be a YAML list. Also check files in System/templates/ for
   field presence, not values: their placeholder values are deliberate.
   Exclude .context/. The seven named exemptions are README.md, AGENTS.md,
   CLAUDE.md, LICENSE, GLOSSARY.md, SPEC.md, and START-HERE.md. List each
   violation.

5. NAMING. Check Markdown content files for lowercase-hyphenated filenames
   with no spaces. Dotfiles and non-Markdown assets are out of scope; exclude
   .context/ and the seven named exemptions above. Require a YYYY-MM-DD- prefix
   on every Record and every dated review file in Action/. Knowledge notes and
   living Action documents are not date-prefixed. List each violation.

REPORTING. Give each check its own PASS or findings section. Translate every
finding for a non-expert and include:
  - what happened, in ordinary language;
  - why it matters;
  - the exact change you propose;
  - whether that change is reversible; and
  - your recommended choice: Fix, Leave unchanged, or Accept as exception.

End with the single most important recommended choice, if any. Ask before
fixing anything. If I choose Accept as exception, remember it with a dated
entry in System/routines/accepted-exceptions.md so it does not reappear as a
new finding each week. The file itself needs normal frontmatter. Every entry
must include: date, file, check number, one-line reason, "approved by <the
human>," and optionally a review date. One entry covers one file and one
check, never a blanket. Creating or updating that list also needs my approval.
```

## When it finds something

- A **modified Record** usually means new information was edited into an old
  capture. The fix that preserves trust is to restore the earlier version, put
  the new information in a new dated Record, and update the Knowledge note
  instead. A deliberate privacy redaction is different: accept and document
  it, and never restore removed sensitive material. Explain deletions and
  renames too; deletion is only legitimate for privacy, and a rename breaks
  links.
- A **Knowledge note with no source list** is a conclusion that can't be
  traced. Ask the agent to find the Record it came from; every Knowledge note
  still needs a nonempty `sources:` frontmatter list.
- A long **QUEUE list** is useful. It shows what the vault may need next; do
  not suppress it.
