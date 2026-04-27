---
type: concept
created: 2026-04-27
updated: 2026-04-27
sources: ["[[LLM-Wiki-Pattern]]"]
tags: [tech/llm, knowledge-management]
---

# RAG vs Compiled Wiki

Two patterns for combining LLMs with document collections. The
distinction is **when synthesis happens**.

## RAG — synthesis at query time

Raw documents are chunked and embedded; on every query the LLM retrieves
relevant chunks and constructs an answer. Examples: [[NotebookLM]],
ChatGPT file uploads, most enterprise document Q&A.

- **Strengths:** zero ingestion cost beyond indexing; works well for
  fact-lookup over large corpora; easy to update (just re-index).
- **Weaknesses:** no accumulation between queries; cross-document
  synthesis is rebuilt every time; contradictions across sources are
  invisible unless the user explicitly asks; the LLM has no memory of
  what it has previously concluded.

## Compiled wiki — synthesis at ingest time

The LLM reads each new source and integrates it into a persistent,
interlinked wiki — updating entity pages, revising summaries, flagging
contradictions, strengthening or challenging the existing synthesis.
Queries read from the wiki, not from raw sources directly.

- **Strengths:** knowledge compounds; cross-references and contradictions
  are pre-computed; the wiki is human-readable independent of any LLM;
  explorations can be filed back so they accumulate too.
- **Weaknesses:** ingest cost is higher per source (the LLM does more
  work per document); requires schema discipline to avoid drift; the
  wiki can grow stale if the maintainer (LLM or human) stops paying
  attention.

## Why this matters

[[LLM-Wiki-Pattern]] argues the bookkeeping burden — the thing that
historically kills wikis — is exactly what LLMs are good at and don't
get bored doing. So the compiled-wiki approach becomes viable for the
first time at the **personal scale**, where it was previously
infeasible because no individual would do that much maintenance.

## See also

- [[LLM-Wiki-Pattern]]
- [[Memex]]
