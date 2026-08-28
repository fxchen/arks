---
updated: 2026-07-21
tags: [routine]
---

# Routine: synthesize

**Trigger:** "synthesize" — after a capture, or batched at the end of a week.

**Steps:**

1. For each person/concept touched by the named Records: find its Knowledge
   note or propose a new one.
2. Draft the updates — one current picture, rewritten in place, every claim
   supported by a Record.
3. Cite the Records in a nonempty `sources:` YAML frontmatter list containing
   their file slugs. Do not use a prose or inline alternative.
4. **Checkpoint: show the before/after and wait for approval before writing
   anything to `Knowledge/`.**
5. After the approved Knowledge writes, flag any `Action/` living doc that
   should change. Show the proposed Action change, wait for approval, and
   change only what the human approves.
