# How finding things works (and when it stops)

An ARKS vault ships with no search engine, and that is not an oversight.

## Tier 0: your agent plus the conventions — the whole stack for a long time

The conventions in [`SPEC.md`](../SPEC.md) §3 are the index. One canonical slug
per person and concept used in every mention, dates on every record, tags in
frontmatter, decisions concentrated in ADRs and living docs — this makes almost
every real question a literal string your agent can find:

- "What did we decide about pricing in March?" → the agent greps
  `pricing`, reads the ADR and the record it cites, answers with sources.
- "Who is Jordan again?" → one file, named the way you'd search for it.

Synthesis is what makes this work: every time Records become Knowledge, the
answer to a future question gets *pre-computed* into one findable, cited
note. A vault whose loop is running doesn't need a search engine — it needs
good filenames, and it already has them.

**Honest threshold:** nobody has benchmarked this. In practice, a hand-authored
vault runs a long time on conventions alone, and the behavioral tells below
matter more than any note count.

## The tells that you've outgrown it

- The agent reads ten-plus files to answer a routine question.
- A fact you *know* is in there comes up empty twice in one week — usually a
  vocabulary miss (the note says "rate card," you asked about "pricing").
- Records start arriving machine-made (transcripts, exports) faster than the
  synthesis loop digests them, so questions must be answered from raw
  material at volume.

## Tier 1 and up: add an engine, under contract

When the tells appear, add a search engine *underneath* the vault — never
inside it. [`SPEC.md`](../SPEC.md) §5 gives the six compatibility principles any
engine must honor (read-only over your Markdown, disposable index, capture only
into `Records/`). If you're comfortable installing a command-line tool, **kb**
is the current recommendation for enhanced search. Its setup notes, caveats,
and the other current known-good options live in
[`05-power-tools.md`](05-power-tools.md).

Adding an engine changes nothing about the method. Removing one loses
nothing but speed. The files remain the system.
