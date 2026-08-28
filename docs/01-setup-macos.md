# Setup, slowly (Mac)

The two steps of the first afternoon that trip people up, taken slowly. The
standing escape hatch for all of it: **paste any error message into a chat
window (Claude or ChatGPT) and ask what it means.** That works for every step
below. The agent can explain the error and propose a next step; you decide
whether to proceed. Before pasting an error anywhere,
remove anything that looks like a password, token, one-time code, long random
string, or personal detail. If you are unsure, ask the agent what to strip.

## 1. A GitHub account and one private repository

1. In your browser: **github.com** → Sign up. Any username is fine.
2. Once you're in: the **+** button (top right) → **New repository**.
3. Name it after the thing you're building (`my-arks` is fine), choose
   **Private**, and click **Create repository**. Done — ignore everything
   the next page suggests; your agent will handle it.

A private repository is access-controlled: it is visible to you, people you
invite, and the service operating it; GitHub processes and stores it.

## 2. An agent on your machine

Claude Code (Anthropic) or Codex (OpenAI). If you already pay for one, use it;
the choice matters far less than starting.

1. Open **Terminal** — press `⌘-space`, type `terminal`, press return. A
   plain text window appears. For everything we do, it's just a text box
   where you type sentences and read replies.
2. In your browser, go directly to the official installation source: Claude
   Code at [code.claude.com/docs](https://code.claude.com/docs/en/setup), or
   Codex at [github.com/openai/codex](https://github.com/openai/codex). Type
   the address yourself rather than clicking search results, then copy-paste
   the install command into the Terminal window. Press return.
3. If anything errors, use the escape hatch — but apply the redaction rule
   above before pasting it into chat.

The first run will ask you to sign in to your AI account in a browser. That is
normal, as are errors — apply the redaction rule above before pasting them into
chat.

## 3. Introduce them, and hand over the rest

1. Make an empty folder wherever you keep things (Desktop is fine).
2. In Terminal, type `cd ` (with the space), **drag the folder onto the
   Terminal window** (this pastes its full location and avoids typing the
   path), press return.
3. Start the agent by typing its name: `claude` (or `codex`). Say hello.
4. From here you talk, it works. Either paste the one-liner —

   > Read github.com/fxchen/arks and help me build my ARKS.

   — or go step by step with
   [`prompts/01-first-afternoon.md`](../prompts/01-first-afternoon.md).

That's the whole setup. You will mostly open Terminal only to start your agent,
and then you talk.
