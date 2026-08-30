# Recover when something looks wrong

Use this when you think the agent, or you, may have broken something in the
vault. Start by finding out what happened; most git problems are easier to
recover from before anyone tries to fix them.

The block below is written for the agent; you can stop reading here and paste
it whole.

```text
Help me understand and safely recover this vault. Diagnose read-only first.
Do not change files, git history, branches, or repository state until I give
explicit consent to the exact fix.

1. Run these read-only commands first, in this order:
     `git status`
     `git log --oneline -10`
     `git diff --stat`
   Before doing anything else, explain in plain words what state the vault is
   in and what appears to have happened. Say what the commands establish and
   what remains uncertain. If more evidence is needed, propose additional
   read-only inspection and explain what it would clarify.

2. Classify the problem as exactly one of these, or say which two overlap:
   - uncommitted changes that look wrong;
   - a bad commit;
   - a missing or renamed file;
   - work that may be lost;
   - a repository operation left half-finished — a merge, rebase, or similar;
     or
   - something outside git, such as disk, sync, or permissions.
   If the state fits none of these categories, say so plainly and stop rather
   than forcing a fit. If it is outside git, stop all changes, state what the
   evidence points to, and give me a concrete next step, such as checking the
   sync client status, running the platform's disk utility, or seeking
   professional help. Do not attempt repair with git commands.

3. Describe the evidence for the classification. Name the affected files and,
   when relevant, the commit. Distinguish tracked changes, untracked files,
   committed history, and anything git cannot see. Do not call work lost until
   the read-only evidence supports that conclusion.

4. Propose the smallest fix that preserves the most work. Explain:
   - exactly what would change;
   - the exact command or file operation you want to use;
   - what would remain untouched;
   - whether the fix is reversible; and
   - how I can verify the result.
   Then ask for explicit consent. Do not run any command that changes state
   unless I approve that exact fix.

5. Follow these rules:
   - Never run `git clean`.
   - Never run `reset --hard` or `checkout -- .` without first listing exactly
     what would be destroyed and getting a yes from me.
   - Never force-push.
   - Never delete `.git`.
   - Never delete untracked files without listing every file first and getting
     my approval for those exact files.
   - Before any approved destructive step, create and verify a rescue copy — a
     stash including untracked files, a temporary branch, or a plain folder
     copy — and tell me where it is.
   - If a secret leaked, rotating or revoking it comes before removing it.
     Follow the privacy exception as stated in this vault's AGENTS.md (the
     external method definition is ARKS SPEC §2.1), and remember that
     removing it from the working tree does not remove it from git history.

6. After an approved fix, rerun the relevant read-only checks and summarize
   the new state in plain words. If the result differs from what you predicted,
   stop, explain the difference, and ask before doing anything else.

A committed vault is a recoverable vault — commit before anything ambitious.
(That covers committed, tracked files. `.context/` and untracked files are
never in git — they need their own backup.)
```
