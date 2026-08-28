# One meeting, end to end

The whole method in one worked example. On a Tuesday, Casey (the fictional
consultant whose vault is in [`template/`](../../template/)) has a 40-minute
call with a client. One event moves through three layers, each with a
different rule for revision.

| Stage | File | Revision rule |
|---:|---|---|
| 1 | The call happens. Nothing is filed yet | — |
| 2 | [`Records/2026-07-21-client-call.md`](../../template/Records/2026-07-21-client-call.md) | Written once, **never edited** |
| 3 | [`Knowledge/people/jordan-at-acme.md`](../../template/Knowledge/people/jordan-at-acme.md) | Rewritten in place; **cites the Record** |
| 4 | [`Action/projects/site-relaunch.md`](../../template/Action/projects/site-relaunch.md) | The **single living document** for the engagement |

Read them in order and notice what moved where:

- **The Record keeps the facts** — who said what, the decision in the words
  it was made in ("we finally got the sign-off Tuesday"), even the small
  human detail (Casey wrote the carousel warning down twice). No
  interpretation. It will read exactly the same in five years — unless
  privacy ever requires a redaction, the one exception that outranks the
  rule.
- **The person note separates fact from interpretation** — observed facts
  from the call sit apart from Casey's one-data-point inference that Jordan
  may prefer to build support before the formal decision. It cites the Record
  in `sources:`, so both the facts and the basis for the inference can be
  traced. Next month it gets rewritten; the Record it points to never does.
- **The project doc tracks the work** — goal, status, constraints, next
  actions. The proposal is due Friday 7/24; when it goes out, this file
  changes. No second status file is ever created.
- The same Record also supports the working hypothesis in
  [`Knowledge/concepts/pricing-model.md`](../../template/Knowledge/concepts/pricing-model.md)
  based on this one call, not a claim of an established pattern. One event
  can feed several notes, and each cites it.

The observation-versus-inference label is deliberate. A person note holds
inferences *about* someone, so label them as inferences, keep them
professional and purposeful, and remember that you may be writing about a
real person who never consented. Write nothing you would be ashamed to show
them.

Why the revision split matters: it prevents the way these systems usually rot
— ten near-identical status files with no way to tell which is current.
Records stay frozen. Knowledge notes are rewritten in place and cite their
Records. Each ongoing effort gets exactly one living Action document. The
folder tells you which rule applies.
