---
type: source
created: 2026-04-27
updated: 2026-04-27
source_path: raw/notes/LLM-Wiki-Pattern.md
tags: [tech/llm, knowledge-management, meta]
---

# LLM Wiki Pattern

A pattern for building personal knowledge bases where the LLM incrementally
constructs and maintains a structured, interlinked wiki — instead of
retrieving from raw documents at query time the way RAG systems do.

## Summary

The starting observation: most LLM-document workflows ([[NotebookLM]],
ChatGPT file uploads, generic RAG) rediscover knowledge from scratch on
every query. There's no accumulation between sessions. A subtle question
still requires the LLM to find and piece together fragments from raw
sources every time. The wiki pattern flips this — when a source is added,
the LLM reads it, integrates it into a persistent collection of
interlinked markdown pages, updates affected entities and concepts, and
flags contradictions. Knowledge is compiled once and kept current.

The key claim is that the **bookkeeping burden is what kills traditional
wikis**, not the reading or thinking. Cross-references, summary updates,
contradiction tracking, consistency across pages — humans give up because
maintenance grows faster than value. LLMs don't get bored, can touch 15
files in one pass, and never forget a cross-reference. The wiki stays
maintained because the cost of maintenance approaches zero.

Architecturally the pattern has three layers. **Raw sources** are
immutable — the LLM reads but never modifies them. **The wiki** is
LLM-generated and LLM-owned: summaries, entity pages, concept pages,
syntheses, all interlinked. **The schema** (a `CLAUDE.md` or `AGENTS.md`
file) encodes conventions and workflows so the LLM behaves like a
disciplined wiki maintainer rather than a generic chatbot. The schema
co-evolves with the user.

The three core operations are **ingest** (read source → discuss → write
summary → update affected pages → log), **query** (search wiki → answer
with citations → optionally file the answer back as a synthesis page),
and **lint** (periodically audit for contradictions, stale claims,
orphans, missing pages, gaps). Critically, query answers can be filed
back into the wiki — explorations compound just like sources do.

The pattern is general: personal knowledge tracking, multi-month research
deep-dives, reading a book chapter-by-chapter, internal team wikis fed by
Slack and meeting transcripts, competitive analysis, due diligence,
course notes, hobby deep-dives. The user curates, asks, prioritizes; the
LLM does everything else.

The pattern is presented as related in spirit to [[Memex]] —
[[Vannevar-Bush]]'s 1945 vision of a personal, curated knowledge store
with associative trails between documents. The part Bush couldn't solve
was who does the maintenance; LLMs are that missing piece.

## Key claims

- LLM + raw documents at query time = re-derivation; LLM + maintained
  wiki = compounding. See [[RAG-vs-Compiled-Wiki]].
- The wiki is a **persistent, compounding artifact** — cross-references
  already there, contradictions already flagged, synthesis already
  reflects everything read.
- The user **never (or rarely) writes the wiki**; the LLM owns generation
  and maintenance.
- A single ingest typically touches **10-15 wiki pages**.
- At moderate scale (~100 sources, ~hundreds of pages) an `index.md` file
  is sufficient — embedding-based search is unnecessary until larger.
- Query answers should be **filed back as synthesis pages** so
  explorations compound.
- Workflow: agent on one screen, [[Obsidian]] on the other —
  > [!quote]
  > Obsidian is the IDE; the LLM is the programmer; the wiki is the
  > codebase.

## Entities and concepts

- [[Memex]] — Vannevar Bush's 1945 concept; spiritual ancestor.
- [[RAG-vs-Compiled-Wiki]] — the central distinction this source draws.
- [[Vannevar-Bush]] — author of the 1945 essay "As We May Think."
- [[Obsidian]] — recommended editor for the wiki layer.

## See also

- [[CLAUDE]] — the schema instantiation for this vault.
- [[index]] — the running catalog the pattern relies on.
- [[log]] — the chronological audit trail.
