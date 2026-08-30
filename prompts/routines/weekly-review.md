# Routine: weekly review

A vault you only write into becomes write-only. This is the fifteen minutes
that keeps the loop running, and it pairs naturally with whatever weekly
moment you already keep: a planning session, shutdown, review, or reset.

The block below is written for the agent; you can stop reading here and paste
it whole.

```text
Run a weekly review of this vault. Review and propose first; do not edit
anything unless I approve the specific change.

1. Run the vault's health-check routine first if it keeps one at
   System/routines/health-check.md, following its read-only checks and approval
   rules. If it has no health-check routine, do a minimal read-only pass
   directly: check that Knowledge notes cite existing Records and resolve
   wikilinks into a queue. Say what was skipped and carry that queue into step
   5. Summarize the result instead of dumping command output: give each check
   its status, the finding that most needs attention, and the
   unresolved-wikilink queue.

2. Find Records that are not yet reflected in the Knowledge notes that should
   cite them. Compare what each Record says with the relevant Knowledge note's
   current content and sources:, paying particular attention to Records newer
   than those notes. List the unsynthesized Records, the Knowledge notes they
   appear to affect, and one sentence about what may need to change.

3. Propose a small synthesis batch from that list. Follow the vault's
   synthesize routine (System/routines/synthesize.md if this vault keeps
   one): show every proposed Knowledge change as
   a short before/after summary and wait for my approval. The Knowledge
   checkpoint still applies; write nothing to Knowledge/ without approval.

4. Review living documents in Action/. Flag any that look stale because their
   updated: date is old relative to the tempo of the effort. Do not invent a
   numeric threshold. For each one, explain the evidence and suggest whether
   to refresh it, close it, or leave it unchanged. Do not edit it yet.

5. From the health check's unresolved-wikilink queue, show the top handful
   worth writing now. Prefer links that recur, support current Action work, or
   block useful synthesis. Briefly explain why each deserves attention; do not
   treat the rest of the queue as errors.

6. Ask me exactly: "what happened this week that never got captured?" Offer
   to file the answer now using the vault's capture routine
   (System/routines/capture.md if this vault keeps one), including its
   privacy scan and write-once Record rules.

7. Close with three concrete suggested next actions, smallest first. Name the
   file or routine involved, the intended result, and where my approval is
   required. Do not begin any of them until I choose.
```

The goal is not an empty queue. It is a trustworthy loop from Records to
Knowledge to Action, with the human still deciding what gets written.
