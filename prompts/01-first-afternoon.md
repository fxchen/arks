# Your first afternoon

Five steps. Nothing here needs prior technical knowledge; the agent carries
the mechanics.
(Stuck on step 1 or 2?
[`../docs/setup-macos.md`](../docs/setup-macos.md) walks through them slowly.)

Before pasting an error anywhere, remove anything that looks like a password,
token, one-time code, long random string, or personal detail. If you're unsure,
ask the agent what to strip before you paste it.

1. **Make a GitHub account and one private repository.** Name it after the
   thing you're building. Choose Private. That's the whole step.

2. **Install an agent.** Claude Code or Codex. Follow the official install
   instructions and copy-paste the command they give you. If something
   errors, use the redaction rule above, then paste the error into a chat
   window and ask what it means.

3. **Introduce them to each other.** Make an empty folder on your computer,
   open the agent inside it, and say:

   > "Set this folder up as a git repository, connect it to my GitHub repo at
   > [paste the link], and help me sign in when GitHub asks."

   Expect a login step. Errors here are normal — use the redaction rule above,
   then paste them back to the agent.
   When it finishes, ask the agent: **show me my repository link** — then open
   it in your browser.

4. **Put five real things in it.** Not a system — just content. A process you
   repeat. A decision you made and the reasoning. Notes from a meeting that
   mattered. Nothing irreplaceable, and no passwords, keys, or account numbers.
   Ugly and unstructured is completely fine; the agent will help you tidy
   later.

5. **Write the house rules together.** `AGENTS.md` is the tool-agnostic house
   rules file. Ask:

   > "Read START-HERE.md at github.com/fxchen/arks, then organize what's here
   > into the four ARKS folders, draft my AGENTS.md house rules in my words —
   > including its safety boundary — and propose the plan before moving
   > anything."

   If you use Claude Code, also ask for a `CLAUDE.md` containing only
   `@AGENTS.md`. Read the draft. Change what's wrong. Those approved rules are
   now the spine of your ARKS. Ask the agent to commit them with your five real
   things, then explicitly approve the push. Open the repository page and
   confirm that the files arrived. That visible copy is your backup actually
   existing.

   *The better version of this step:* skip drafting from scratch and paste
   [`build-my-vault.md`](build-my-vault.md) instead — the agent interviews you
   and builds the structure around your answers.

## Then stop building and start using

Take one real task this week — something you'd have done by hand anyway — and
do it here instead. The structure should grow out of use, not ahead of it.
Every system that gets designed in full before anyone uses it gets abandoned.
