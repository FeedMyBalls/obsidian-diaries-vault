---
type: entity
created: 2026-04-27
updated: 2026-04-27
sources: ["[[LLM-Wiki-Pattern]]"]
tags: [tools, software]
---

# Obsidian

Local-first markdown editor with bidirectional `[[wikilinks]]`, a graph
view, and a plugin ecosystem. The recommended editor for this vault.

Per [[LLM-Wiki-Pattern]], the typical workflow runs the LLM agent on one
side and Obsidian on the other — the LLM edits files, the user browses
the result in real time, following links and using the graph view to see
structure.

> [!quote]
> Obsidian is the IDE; the LLM is the programmer; the wiki is the
> codebase.
> — [[LLM-Wiki-Pattern]]

## Useful plugins / features

- **Graph view** — see wiki shape, hubs, and orphans at a glance.
- **Web Clipper** (browser extension) — converts web pages to clean
  markdown; output goes to `raw/articles/`.
- **Marp** plugin — markdown-based slide decks, useful for synthesis
  outputs.
- **Dataview** plugin — queries over YAML frontmatter; can render
  dynamic tables (e.g. "all sources tagged `tech/llm`").

## Configuration notes

- Set Settings → Files and links → "Attachment folder path" to
  `raw/assets/` so downloaded images land there.
- Bind a hotkey to "Download attachments for current file" (Settings →
  Hotkeys, search "Download") to pull image URLs to local disk after
  web-clipping an article. Useful because the LLM can't natively read
  inline images in markdown — local copies let it view them on demand.

## See also

- [[LLM-Wiki-Pattern]]
