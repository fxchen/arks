# Routine: synthesize

Use this to turn write-once Records into current Knowledge. Run it after a
capture, or batch it at the end of a week.

```text
Synthesize the following Record(s) into Knowledge: [name the Records/ files,
or say "everything captured since the last synthesis"].

1. For each person and concept the Records touch: find its Knowledge note, or
   propose a new one (Knowledge/people/... or Knowledge/concepts/...).
2. Draft the updates: what changed in our understanding, stated plainly.
   Rewrite in place — a Knowledge note is one current picture, not a log.
3. Every updated note must cite its sources in one required form: a nonempty
   sources: YAML frontmatter list containing the Record file slugs. Do not use
   a prose or inline alternative. Extract, don't invent — if the Record doesn't
   support a claim, it doesn't go in.
4. THE CHECKPOINT: show me every proposed update as a short before/after
   summary and WAIT for my approval before writing anything to Knowledge/.
5. After I approve: write the Knowledge notes. Then flag exactly what, if
   anything, should change in any Action/ living document. Change an Action/
   document only after I explicitly approve that change.
```

This routine preserves the data flow: write-once Records feed Knowledge, and
Knowledge informs Action. The approval checkpoint keeps Knowledge changes
under your control.
