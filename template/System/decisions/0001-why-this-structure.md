---
updated: 2026-07-21
tags: [decision, adr]
---

# 0001 — Why this vault is structured the way it is

**Status:** accepted · **Date:** 2026-07-21

## Context

I kept losing what I knew: meeting insights buried in old chat transcripts,
three versions of every status doc, and every AI conversation starting from
zero because nothing persisted anywhere a model could read.

## Decision

Adopt the ARKS pattern (github.com/fxchen/arks): four folders split by
revision rule — append-only `Records/`, overwritable-but-cited `Knowledge/`,
one-living-doc `Action/`, durable `System/` — with a root `AGENTS.md` the
agent reads every session, and information flowing one direction only.

## Consequences

- Anything I might want to trust later goes into a dated record first, even
  when it's faster to just update a conclusion.
- The agent proposes before writing to `Knowledge/` — slightly slower, and
  the reason the vault stays mine.
- If a status question has two answers, that's a bug: the effort's single
  living doc in `Action/` is the answer.

## Alternatives considered

A notes app (harder for an agent to operate directly; some format lock-in);
one big MEMORY.md (worked for two weeks, then overflowed); no system (the
default, and the thing this replaces).
