# Log

Chronological record of wiki operations. Append-only. New entries go at
the **bottom**.

Entry header format (exact, for grep-ability):

```
## [YYYY-MM-DD] <op> | <Title>
```

Where `<op>` is one of: `ingest`, `query`, `synthesis`, `lint`, `note`.

Quick views from CLI:

```bash
grep "^## \[" log.md | tail -10        # last 10 events
grep "^## \[.*ingest" log.md           # all ingests
grep "^## \[2026-04" log.md            # all April 2026 events
```

---

## [2026-04-27] note | Vault initialized

Schema, index, and log scaffolded by Claude. Folder layout created:
`raw/{articles,papers,notes,assets}` and `wiki/{sources,entities,concepts,synthesis}`.
See [[CLAUDE]] for conventions. Ready for first ingest.

## [2026-04-27] ingest | LLM-Wiki-Pattern

First ingest. Source: `raw/notes/LLM-Wiki-Pattern.md` (the foundational
idea file describing this vault's pattern itself). Wrote
[[LLM-Wiki-Pattern]] (source summary). Created [[Memex]],
[[RAG-vs-Compiled-Wiki]] (concepts), [[Vannevar-Bush]], [[Obsidian]]
(entities). Index updated. 5 wiki pages from 1 source — kept lean per
schema; pages will fill out as more sources arrive.

## [2026-04-27] schema | Personal-second-brain scope + hard rules

[[CLAUDE]] updated to scope this vault as a personal second brain
(diaries, life-tracking, school/career, projects incl. [[Neo-OS]],
long-term memory). Added §"Hard rules (binding)" — raw immutability,
diary handling, contradictions preserved, co-authored synthesis pages,
git commit discipline. Added §"Diary handling" with monthly-rollup
pattern and ≥3-entry threshold for theme promotion. Added folders
`raw/diary/` and `wiki/projects/`. Configured Obsidian
`attachmentFolderPath: raw/assets`. Removed default `Welcome.md`.
Initialized git repo on `main` with `.gitignore` (excludes
`workspace.json`).
