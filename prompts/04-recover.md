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
   - work that may be lost; or
   - something outside git, such as disk, sync, or permissions.
   If it is outside git, stop and say so plainly. Do not pretend a git command
   can repair a disk, sync, or permissions problem.

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
   - Never run `reset --hard` or `checkout -- .` without first listing exactly
     what would be destroyed and getting a yes from me.
   - Never force-push.
   - Never delete `.git`.
   - Never delete untracked files without listing every file first and getting
     my approval for those exact files.
   - If a secret leaked, rotating or revoking it comes before removing it.
     Follow this vault's privacy exception (in AGENTS.md; the rule's home is
     the ARKS spec, SPEC.md §2.1), and remember that removing it from the
     working tree does not remove it from git history.

6. After an approved fix, rerun the relevant read-only checks and summarize
   the new state in plain words. If the result differs from what you predicted,
   stop, explain the difference, and ask before doing anything else.

A committed vault is a recoverable vault — commit before anything ambitious.
```
