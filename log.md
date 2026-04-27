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

## [2026-04-27] ingest | Diary corpus 2023-2026

39 diary entries from user's `Things About Neo` folder copied to
`raw/diary/{2023..2026}/` and ingested. One source page per entry
(39 pages in `wiki/sources/`), filename `YYYY-MM-DD-Title.md`. Year-
by-year discussion before writing each batch; entity/concept deltas
surfaced after each year for user review. `2025/facets.txt` dropped
as exact duplicate of `2025/7-minutes.txt`. Two image assets
(`Long-Term-Plan.jpg`, `Spring-2026-Schedule.PNG`) copied to
`raw/assets/`. The corpus does *not* fit the routine-daily-entry
shape covered by the monthly-rollup pattern in [[CLAUDE]] §Diary
handling — most entries are intense-emotional-events or major-decision
register and get dedicated pages per the schema's exception clause.

## [2026-04-27] note | Concept naming pass

User-led naming pass during ingest. Renames: `Birth-Origin-Myth` →
[[Umbilical-Origin-Story]]; `/pol/-Vocabulary` → [[Blackpill-Vocabulary]];
`Black-Market-Drug-Acquisition` → [[Illicit-Acquisition]];
`Manic-Depressive-Oscillation` → [[Mood-Cycling]];
`Time-Perception-Meditation` → [[Seven-Minute-Window]];
`Loophole-Operating` → [[System-Gaming]];
`10-Year-Plan` merged into [[Long-Term-Plan]] (verbal alias preserved);
`Eddy` merged into [[Edd]]. Drops: `K-12-Bubble`. Folds:
`Erikson-Stages` into [[Romantic-Obsession-Architecture]];
*Inferiority-Superiority-Oscillation*, *Spectator-Self*, and
*Hidden-Good-Kid/Hidden-Bad-Kid* into [[Living-Contradiction]] as
named sections.

## [2026-04-27] synthesis | Concept pages built

47 new pages in `wiki/concepts/` across 6 user-defined domains
(self-perception, relationships, behavior patterns, ideology, method,
events). Foundational pages built first per user instruction:
[[Living-Contradiction]], [[GC-Scandal-2021]],
[[Romantic-Obsession-Architecture]], [[Savior-Complex]]. All cite
source pages in frontmatter `sources:`; inline `[[wikilinks]]` per
schema. Total `wiki/concepts/` count: 49 (47 new + 2 pre-existing).
Per-page quality: terse-and-factual register; quotes via `> [!quote]`
callouts; inferences labeled. Calibration pass for absolute-language
("is" / "always") deferred to lint.

## [2026-04-27] note | Long-Term-Plan project page

Built `wiki/projects/Long-Term-Plan.md` from `raw/assets/Long-Term-Plan.jpg`
+ 6 source pages ([[2024-07-22-First-Day-Of-Work]], [[2024-09-04-Life-So-Far]],
[[2025-05-12-Inaction-And-Regret]], [[2026-03-14-March-14-2026-19-Years]],
[[2026-03-17-High-School-Graduation]], [[2026-03-29-Savior-Complex-Blabber]]).
Cross-linked to [[Savior-Complex]] per standing instruction
("medicine = savior-complex made operational"). Replaces empty stub.

## [2026-04-27] note | Vault stub cleanup

Empty `.md` stubs auto-created by Obsidian wikilink clicks were
swept from vault root into proper `wiki/{entities,concepts,projects}/`
locations across multiple passes during the build:
[[Anette]], [[D]], [[Ryan]], [[Skye]] → entities;
[[GC-Scandal-2021]] → concepts; [[Long-Term-Plan]],
[[Youtube-Channel]] → projects; [[Hollow-Knight]], [[ULTRAKILL]] →
entities; `2024-01-06-Cant-Get-Over-Her.md` → sources (overwritten
when proper page was written). Five empty `raw/notes/diary/` year
folders (created in error from a path-typo early in the session)
remain at the user's discretion to delete via Obsidian/Explorer
since bash on the mounted drive lacks delete permission.

## [2026-04-27] note | Index updated

`index.md` rewritten to reflect 40 sources, 49 concepts, 8 entities,
3 projects (incl. [[Neo-OS]] flag), 0 synthesis. Concepts organized
into 7 sub-sections (the 6 user-defined domains + a Wiki/meta
sub-section for [[Memex]] and [[RAG-vs-Compiled-Wiki]]).
Alphabetical within each sub-section.

## [2026-04-27] synthesis | Entity pages built

User-directed entity-page push. 49 new pages in `wiki/entities/`
across 8 sub-categories per user calls (family, crushes/partners,
friends, coworkers, school staff, cultural references, public
figures, places). Substantive vs minimal treatment per user's
calls in the entity-list-surface review. Notable structural calls
applied: [[Vice-Principal]] folded into [[Vice-Principal-Incident]]
concept (no entity); [[Social-Worker]] built as concept rather than
entity (institutional role over specific person); /pol/ and /r9k/
folded into [[4chan]]; TikTok/Reels/Twitter folded into
[[Doomscrolling-Period]]; Robinhood folded into [[Trading-Addiction]];
Technoblade/Videogamedunkey/Pyro folded into [[Youtube-Channel]];
[[Pre-Calc-Wizz-Girl]] kept as unattributed reference (no page);
4chan e-girl persona, Genghis-Khan, hidden-boyfriend, Baby-Sister
all folded or no-page per user calls. [[Anette]] entity holds 2025
vs. 2026 voice contradiction in tension via `> [!warning]`
callout. [[K]] page filed restrainedly per user's "felt truth not
corrected version" decision; the structural fragility of the
GC-rape causal chain flagged inline without resolving. Total
`wiki/entities/` count: 53 (49 new + 2 pre-existing + 2 carry-over
stubs Ryan / Skye).

## [2026-04-27] note | Project pages built

[[Youtube-Channel]] project page filled in (replaced empty stub);
[[Long-Term-Plan]] previously logged. [[Neo-OS]] minimal stub built
with brief scope description from user — Neo will flesh out
independently. Total `wiki/projects/` count: 3.

## [2026-04-27] synthesis | Social-Worker concept page

Built `wiki/concepts/Social-Worker.md` as concept (institutional
role) rather than entity (specific person), per user's call. The
recurring failure-of-support pattern across the Oct 2023 and
April 2024 sessions warrants concept-level treatment; the specific
identity of the counselor does not. Cross-linked to
[[Suicidal-Drawing-Incident]], [[Vice-Principal-Incident]],
[[AI-Companionship]] (the documented substitute), and
[[Method-Research]]. Concept count now 50.

## [2026-04-27] note | Index updated (second pass)

`index.md` rewritten again to reflect post-entity-build state: 40
sources, 50 concepts, 53 entities (organized into 8 sub-categories
matching user's entity-list framing + a Stubs sub-section for
[[Ryan]] and [[Skye]]), 3 projects, 0 synthesis. Synthesis section
notes that `About-Me` / `Current-State` / `Stable-Facts` /
`Open-Questions` require outline-in-chat per [[CLAUDE]] §Hard
rules ¶4 — none initiated.
