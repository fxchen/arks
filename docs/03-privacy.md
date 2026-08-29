# Privacy, in plain terms

Privacy here is a set of boundaries and habits, not a property the vault gets
just because its repository is private. This page is a threat model — a plain
account of who can receive your information, what can go wrong, and where you
still have to make a decision.

## What a private repository protects

A private repository provides access control. Its contents are visible to you,
people you invite, and the service operating it. GitHub processes and stores
the repository.

Private does not mean end-to-end encrypted. End-to-end encryption would keep
the service operating the repository from being able to read the contents.
That is not the protection a private GitHub repository provides.

A private repository reduces public exposure. It does not protect you if
someone gains access to your GitHub account or computer, if you invite the
wrong person, or if a tool with access reads the files. It also does not undo
information that has already been copied, shared, or committed.

## What reaches your AI provider

Everything your agent reads reaches the AI provider that runs it. That can
include vault files, text pasted into chat, command output, and error messages.
The privacy boundary follows what the agent reads, not only what you type into
the chat window.

Retention and training practices vary by provider and by plan. Check the data
settings and current terms for the account you use. Make that check before you
let the agent read material whose exposure would matter.

## Writing about other people

The people in your notes may never have consented to being written about. Keep
observed fact separate from inference — what you directly saw or heard apart
from what you think it may mean.

Keep those notes professional and purposeful. Write nothing you would be
ashamed to show the person. Sensitive material about someone else deserves a
deliberate decision about whether it belongs in the vault at all.

## Secrets do not belong in files

Passwords, access keys, account numbers, one-time codes, and similar secrets
never go in any file. A `.gitignore` pattern tells git not to track selected
files, which can help prevent accidents. It is not the defense. The defense is
the habit of keeping secrets out before a file is created or pasted.

If a secret lands in a file anyway, rotate or revoke it first — replace it or
disable it so the exposed value no longer works. Then redact it from the file.
The working tree, meaning the files you see now, is not the whole record. Git
history can retain content deleted from the working tree, and existing copies
of the repository can retain it too.

The rule that privacy overrides the normal write-once treatment of Records,
including how to note a redaction, remains in
[SPEC.md §2.1](../SPEC.md). That section is the authority if this guide and the
spec ever differ.

## Use a separate repository when needed

Material that is appropriate to keep but too sensitive for the main vault can
live in a second private repository. Open that repository only when you need
it, and give the agent access only during that work.

This pattern reduces routine exposure. It does not change who operates the
repository or what reaches the AI provider when the agent reads it.

## Employer and client material

Work material may be governed by an employment agreement, a client contract,
or a nondisclosure agreement — an NDA, which limits what you may disclose.
Putting that material in a personal vault is a decision to make deliberately,
not an automatic part of capture.

Read the terms that apply. If the boundary is unclear, the next step may be a
conversation with your employer, client, or another person authorized to make
the call. Keep one client's material out of another client's work.

## Redact errors before pasting

Before pasting an error into chat, remove anything that looks like a password,
token, one-time code, long random string, or personal detail. The full
redaction rule lives in the setup guides:
[Mac](01-setup-macos.md) and [Windows](02-setup-windows.md).

## Nothing leaves without a fresh yes

Reading and organizing files inside the vault is different from sending them
elsewhere. Sending, publishing, posting, sharing, connecting an account, or
changing repository visibility requires your fresh explicit yes each time.

That standing permission rule belongs in your vault's `AGENTS.md`. The
[starter `AGENTS.md`](../template/AGENTS.md) includes the language to preserve
when you adapt it for your own vault.
