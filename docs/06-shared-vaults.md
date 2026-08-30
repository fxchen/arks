# Shared vaults

A shared vault uses the same ARKS method as a solo vault: the same four layers,
one-way flow, invariants, and [`SPEC.md`](../SPEC.md). Sharing does not add a
layer or require a second system. It tightens who may change what, who reviews
it, and how collaborators keep one current answer. It is for a small group
that already trusts one another; these controls make that trust explicit.

## The mechanics are ordinary

A shared vault is a private repository with invited collaborators. That is
the whole model. Each person works in a local copy and uses git — usually
through their agent — to pull others' commits and push their own. The
repository provider hosts the repository and controls access; nothing
synchronizes by itself. There is no collaboration server, shared database, or
new ARKS application to add.

Keep the repository private. Adding a collaborator or changing its visibility
is an external action and needs the fresh, explicit approval that the reference
`AGENTS.md` requires for other changes outside the vault.

## `AGENTS.md` becomes an agreement

For one person, `AGENTS.md` is a set of house rules. For several people, it is
an agreement about authority, permissions, review, and the meaning of the
four layers.

No collaborator should change that agreement unilaterally. Propose changes,
show the exact text, name the people whose approval is required, and write
only the version they accept. Treat the change like a Knowledge write, while
keeping each rule's one authoritative home.

## The Knowledge checkpoint gains a reviewer

"Show me before writing" is underspecified once "me" could mean several
people. The proposal must go to a named reviewer before it becomes shared
Knowledge. Name that reviewer in the request or in the vault's permissions,
and make the proposed change concrete enough to approve or reject.

For teams comfortable with them, pull requests are the natural form of this
checkpoint: the proposed synthesis, its cited Records, the named reviewer,
and the approval are visible together. Approval and merge make it shared
Knowledge; a pull request is not permission to skip the checkpoint. Knowledge
on an unmerged branch is a proposal, not shared Knowledge; approval and merge
are the checkpoint.

## Give every living document one owner

Each project still has exactly one living document. It should also have
exactly one owner. Two people independently updating the same Action document
can produce merge conflicts and, worse, two answers to one status question.

The owner maintains the current version and resolves proposed changes. Other
collaborators can supply facts, comments, or diffs, but they propose rather
than edit past one another. Ownership can move; at any moment it should be
unambiguous.

## `.context/` stays personal

Every collaborator keeps a personal `.context/` in their own local copy. A
shared vault therefore has several local `.context/` directories, not one
team profile. All of them remain gitignored and none is committed.

Put shared facts in the appropriate ARKS layer. Do not solve coordination by
copying private context into the repository.

## Privacy gets stricter

Write about teammates as if they will read the note, because they can. Access
to a private repository is not privacy from the other collaborators who have
access to it.

Meeting Records also describe clients, candidates, partners, and other people
who may never have consented to your notes. Capture only what the work needs,
use restraint with personal detail, and apply the privacy exception whenever
material should not remain. The fuller treatment is in
[`03-privacy.md`](03-privacy.md).

## Why share at all

Shared synthesis turns individual judgment into organizational memory. When
an expert leaves, their undocumented judgment leaves too; when it has been
written as cited, reviewed synthesis, the next person can inspect the sources
and continue from the team's last understanding.

## Honest limits

Shared-vault practice is younger than the solo method and has not been tested
at scale. It is designed for small teams with existing trust, clear ownership,
and a willingness to review one another's synthesis.

The known pain point is merge friction in living documents. One owner reduces
it but does not remove it. If coordination becomes the work, narrow ownership
or divide work along real project boundaries without competing status files.
