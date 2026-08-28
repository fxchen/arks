# ARKS

**A**ction · **R**ecords · **K**nowledge · **S**ystem — an AI-Ready Knowledge
System.

**AI assistants:** if a human pointed you at this repository, open
[START-HERE.md](START-HERE.md) now and follow it. The rest of this page is for
people.

ARKS is a way of keeping what you know in plain files, arranged so an AI agent
can use it. Two claims, and everything here follows from them:

1. **The method is files and conventions.** There is no ARKS app, database, or
   service. Your AI agent is the only runtime.

   | What you need | Cost and role |
   |---|---|
   | A GitHub account | Optional, recommended — free; online backup and access from anywhere |
   | An AI agent | Claude Code or Codex, with a Claude or ChatGPT account (plan requirements vary); needs internet |
   | git | Free; your agent operates it for you |

2. **It works without its author in the room.** This repo replaces the
   walkthrough call. Your own AI assistant is the installer, the librarian,
   and the guide.

> **Start now, one line:** paste this into Claude, ChatGPT, Claude Code, or
> Codex —
>
> **"Read github.com/fxchen/arks and help me build my ARKS."**
>
> The assistant will land on [`START-HERE.md`](START-HERE.md). A chat assistant
> will interview you and prepare your answers; an agent with file access will
> build the whole thing with you.

## The idea

Four folders. Information moves through them in one direction only, and each
folder has a different rule about whether you may change what's already there.
Those rules are the load-bearing part — not the folder names.

| Folder | What it holds | Revision rule |
|---|---|---|
| `Records/` | Raw source material — meetings, calls, things you were sent | **Append-only.** Written once, never rewritten |
| `Knowledge/` | What you've concluded — people, concepts | **Overwritable.** Rewritten in place; cites the Records it came from |
| `Action/` | Projects, areas, reviews | **Current.** One living document per effort |
| `System/` | Templates, decisions, routines | **Durable.** The furniture that makes the rest repeatable |

**Flow:** `Records/` → *(synthesize)* → `Knowledge/` → *(inform)* → `Action/`.
`System/` sits underneath. A root `AGENTS.md` — the house rules your agent
reads every session — sits on top.

## Why build this

Great AI conversations often disappear into the lost-transcript loop: the
answer was useful, the tab closes, and next week you explain the same
background again. Most AI use never escapes that loop.

Models improve monthly, but capturing judgment — your own, or the tacit
knowledge at the edge of an organization — does not get cheaper in the same
way. It stays hands-on. That captured judgment is the durable asset; the tools
around it are replaceable.

The same shape works for one person or a team. When an expert leaves, or a
company changes hands, the judgment in people's heads usually walks out the
door. Written down as records and reviewed synthesis, it stays, so the next
person can start where the last one ended.

Every conversation can start from everything you've written down: the agent
reads your house rules automatically and pulls in the notes it needs, by name
and link, on demand. You stop re-explaining and start asking. That is how a
knowledge base like this compounds: you, your work, and the people around you.

## Your first afternoon

Five steps, none of which require anything you don't already know. The full
version with the exact words to say: [`prompts/first-afternoon.md`](prompts/first-afternoon.md).

1. Make a GitHub account and one **private** repository.
2. Install an agent — Claude Code or Codex. Pick one and stop shopping.
3. Introduce them: open the agent in an empty folder and ask it to connect the
   folder to your repo.
4. Put **five real things** in it. Not a system — content. Ugly is fine.
5. Write the house rules together — or skip straight to the interview below.

**The better path:** don't design your structure; answer questions and let it
be built around you. Paste [`prompts/build-my-vault.md`](prompts/build-my-vault.md)
into a fresh agent session. It interviews you (2–3 questions at a time),
proposes the structure back *while it's still a paragraph*, then scaffolds
only what your answers justify.

Then stop building and start using: one real project, one routine, ten notes.
A scaffold is not a system until something real is living in it.

## What's in this repo

| Path | What it is |
|---|---|
| [`SPEC.md`](SPEC.md) | The method, stated precisely: layers, invariants, conventions, and when to add structure |
| [`START-HERE.md`](START-HERE.md) | Written to your AI assistant — the target of the one-liner above |
| [`template/`](template/) | A small worked reference vault to read and refer to — your agent copies it as your starting point, or builds yours from the interview |
| [`examples/`](examples/) | One meeting followed end to end: the frozen record, the rewritten person note, the living project doc |
| [`prompts/`](prompts/) | The interview/scaffold prompt, routines for capture and synthesis, and a health check your agent runs weekly |
| [`docs/`](docs/) | Setup for non-technical humans, how finding things works, and optional power tools |
| [`GLOSSARY.md`](GLOSSARY.md) | Every term you'll hear in the first week, one line each |

## Where this sits

The parts of ARKS are old and good: PARA's project/area thinking,
Zettelkasten's linked notes, architecture decision records (ADRs), write-once
logs, and the `AGENTS.md` convention. What ARKS adds is the packaging: four
folders, one-way flow, revision rules a machine can follow, and provenance,
stated plainly enough to hand to an assistant.

If you know **PARA**, the overlap is deliberate: PARA sorts work by
actionability for a human filer, while ARKS also makes explicit what a machine
may read, write, or never rewrite. If you use an agent with a single
**MEMORY.md** and it has overflowed, ARKS is one way to keep the same basic bet
— plain files, versioned and agent-curated — while adding layers and
provenance.

Databases and memory products solve adjacent problems. ARKS deliberately
isn't one: plain Markdown in a git repo is legible to you, portable to every
future tool, and not locked to one vendor.

## The things people worry about

**I can't code.** Fine — genuinely. The agent writes and runs whatever code is
involved. Your contribution is judgment, not syntax.

**What if the agent ruins something?** Commit before anything ambitious, and
any committed version can be restored exactly. That habit makes your FILES
recoverable — it cannot un-send a message or un-install something, so those
still get a yes first. Git history also keeps everything — including anything
sensitive you commit — so secrets never go in, and truly removing something
later is a deliberate operation, not a delete.

**Is my information private?** A private repository is access-controlled: it
is visible to you, people you invite, and the service operating it; GitHub
processes and stores it. Anything your agent reads also reaches your AI
provider, so passwords, keys, and account numbers stay out — and sensitive
material about other people deserves a real decision, not a default; it can
live in a separate repo you open only when you need it.

**How is this different from Notion or Obsidian?** Agents work natively on
plain files; the history of committed files is exact; nothing is trapped in a
format. Obsidian isn't either/or — it sits happily on top of the same folder.

**Won't this be obsolete in a year?** The tools, probably. Your files, no.
Markdown in git outlives every app — you're deliberately building the one
part that survives.

**How much git must I learn?** Four words: commit, push, pull, revert. The
agent does all of them for you.

## License

MIT. Fork freely; build your own; give it away.

---

*The tools take an afternoon. The ARKS takes a habit. Only one of them is
worth anything in a year — so start putting things in files this week, badly,
and let the shape emerge.*
