# Jargon decoder

Everything you'll hear in the first week, in one place.

| Term | Meaning |
|---|---|
| **repo / repository** | A folder where git tracks the history of committed files. |
| **git** | The version-control system that tracks changes to files on your computer. |
| **GitHub** | A website that hosts repos online; it is separate from git. |
| **commit** | A save point, with a note saying what changed. |
| **push / pull** | Push sends commits to GitHub; pull brings remote commits to your computer. |
| **clone** | Download a full copy of a repo, history included. |
| **branch** | A parallel version for trying changes without changing the main version. |
| **pull request** | A proposal to review changes before they join the main version. |
| **merge** | Combine approved changes into the main version. |
| **merge conflict** | Git cannot combine two sets of edits by itself and asks a human. |
| **diff** | A line-by-line view of what changed. |
| **Markdown (`.md`)** | Plain text with light formatting marks. `#` for a heading, `-` for a bullet. |
| **`README.md`** | The front door of a repo — the first thing a person or agent reads. |
| **`CLAUDE.md` / `AGENTS.md`** | `AGENTS.md` is the standing-instructions file assistants read; `CLAUDE.md` is a one-line loader for Claude Code. |
| **frontmatter** | A metadata block at the top of a file holding fields such as its date and tags. |
| **write-once** | A file in `Records/` that is never changed after filing — corrections are new Records; the one exception is deliberate privacy redaction; renaming to correct a wrong date or slug is allowed with approval — the content never changes. |
| **append-only collection** | `Records/` as a whole: you may add files, never rewrite existing ones. |
| **routine** | A saved instruction for a repeated job — a Markdown file you paste or point your agent at. |
| **vault** | Your folder of knowledge — the repository's contents. |
| **living document** | The single always-current file for an ongoing effort. |
| **slug** | The lowercase-hyphenated filename that identifies a note, used inside `[[wikilinks]]`. |
| **wikilink** | A name in `[[double brackets]]` that links a mention to a note. |
| **ADR** | A short note recording a decision and its rationale for future reference. |
| **terminal / CLI** | A text interface where you run the agent and enter commands. |
| **agent** | An AI that can take actions — read, write, and run commands — not only produce text. |
| **capture** | File raw source material as a dated, write-once Record. |
| **synthesis / synthesize** | Turn Records into current Knowledge, with human approval before writing it. |
| **provenance** | The trace from a Knowledge note back to its source Records through the required `sources:` list. |
| **invariant** | A load-bearing rule that every conforming ARKS vault must keep. |
| **scaffold** | The initial folders and files built for a vault from the person's actual needs. |
| **redaction** | Deliberate removal of sensitive, dangerous, or legally removable material; the privacy exception to write-once. |
| **tombstone** | A one-line note left in a Record to mark that material was redacted. |
| **graduation trigger** | The condition that justifies adding a piece of optional structure. |
| **health check** | The weekly five-check audit that finds departures from the vault's rules and reports them before fixing anything. |
| **`.context/` / private layer** | A per-person folder for context and scratch work that git is told never to commit — a sharing convention, not encryption or access control. |
| **engine** | Optional search or capture tooling over authored files. |
| **index** | The disposable lookup data an engine builds — authored files remain the source of truth. |
| **OODA** | John Boyd's observe–orient–decide–act loop, mapped in ARKS to capture, synthesis, the human checkpoint, and Action. |
