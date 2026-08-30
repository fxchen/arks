# Your first afternoon

These five steps ask you to choose the content and approve changes. The agent
handles the command-line and Git mechanics.
If you get stuck on step 1 or 2, use
[`../docs/01-setup-macos.md`](../docs/01-setup-macos.md) on a Mac or
[`../docs/02-setup-windows.md`](../docs/02-setup-windows.md) on Windows. Each
walks through them step by step.

Before pasting an error anywhere, remove anything that looks like a password,
token, one-time code, long random string, or personal detail. If you're unsure,
ask the agent what to strip before you paste it.

1. **Make a GitHub account and one private repository.** Name it after the
   thing you're building. Choose Private; no other setup is needed yet.
   (No GitHub? Skip this step and the connection in step 3 — the vault works
   locally; you just have no online backup until you add one.)

2. **Install an agent.** Claude Code or Codex. Follow the official install
   instructions and copy-paste the command they give you. If something
   errors, use the redaction rule above, then paste the error into a chat
   window and ask what it means.

3. **Connect the folder to GitHub.** Make an empty folder on your computer,
   open the agent inside it, and say:

   > "Set this folder up as a git repository, connect it to my GitHub repo at
   > [paste the link], and help me sign in when GitHub asks."

   The agent will check what name your save history is written under — on a
   hand-me-down or family computer it may be someone else's, and it should be
   yours.

   Expect a login step. Errors here are normal — use the redaction rule above,
   then paste them back to the agent.
   When it finishes, ask the agent: **show me my repository link** — then open
   it in your browser.

4. **Put five real things in it.** Not a system — just content. A process you
   repeat. A decision you made and the reasoning. Notes from a meeting that
   mattered. Nothing irreplaceable, and no passwords, keys, or account numbers.
   Leave the material unstructured for now; the agent can help you organize it
   later.

5. **Write the house rules together.** `AGENTS.md` is the tool-agnostic house
   rules file. Ask:

   > "Read START-HERE.md at github.com/fxchen/arks, then organize what's here
   > into the four ARKS folders, draft my AGENTS.md house rules in my words —
   > including its safety boundary — and propose the plan before moving
   > anything."

   If you use Claude Code, also ask for a `CLAUDE.md` containing only
   `@AGENTS.md`. Read the draft. Change what's wrong. The rules take effect
   when you say they are right — say so in so many words. Once approved, those
   rules govern your ARKS. Ask the agent to commit them with your five real
   things, then explicitly approve the push. Open the repository page and
   confirm that the files arrived. The backup is verified only when you can
   see the files there.

   To build a tailored starting structure, skip drafting from scratch and
   paste [`02-build-my-vault.md`](02-build-my-vault.md) instead — the agent interviews
   you and builds the structure around your answers.

## Then stop building and start using

Take one real task this week — something you'd have done by hand anyway — and
do it here instead. The structure should grow out of use, not ahead of it.
Every system that gets designed in full before anyone uses it gets abandoned.
