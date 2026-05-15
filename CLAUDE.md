# CLAUDE.md — markup-foundations

This is a **knowledge workspace**, not an agentic project. There are no agents, no build pipeline, no scheduled tasks. The only thing here is durable notes on markup foundations and the conventions that keep them organized.

If you (any agent, or future-me) are editing files here, follow the conventions below.

## Purpose

Personal reference vault on first principles of markup for content authoring: markdown, Markdoc, MDX, HTML-in-markdown, shortcode lineage, keystroke-time expansion, SSG authoring stacks, Obsidian/Logseq syntax. See `README.md` for full scope.

## Knowledge gradient

All notes live in `knowledge-base/` and use the **temperature gradient** — five numbered zones from hot to cold:

```
task_plan.md   00-inbox/   01-working/   02-learnings/   03-reference/   04-archive/
   (hot)       (warm)        (active)       (cool)         (cold)        (frozen)
```

- **`00-inbox/`** — raw captures, unprocessed
- **`01-working/`** — drafts, active synthesis, opinions in formation
- **`02-learnings/`** — distilled atomic insights, dated (`YYYY-MM-DD-topic.md`)
- **`03-reference/`** — stable, actively-consulted survey docs and guides
- **`04-archive/`** — filed knowledge (optional Johnny Decimal)

Content can **skip zones** — a distilled insight can land directly in `02-learnings/`. Flow direction is always hot → cold. See `knowledge-base/README.md` for full spec.

## File format

All knowledge-base files use **Obsidian Flavored Markdown** with this frontmatter:

```yaml
---
date created: YYYY-MM-DD
date modified: YYYY-MM-DD
temperature: inbox | working | learnings | reference | archive
tags:
  - topic
aliases: []
related:
  - "[[Other Note]]"
---
```

Use wikilinks (`[[note-name]]`) to cross-reference between zones. Use callouts (`> [!tip]`, `> [!note]`) for emphasis.

## Conventions

- **Default to `00-inbox/`** for any new capture you're unsure about. Better to capture warm than lose.
- **Distilled means atomic.** A learning is one insight per file. If two ideas fight for the same note, split them.
- **Link, don't duplicate.** A reference doc can wikilink to relevant learnings instead of restating them.
- **Out-of-scope material gets linked, not mirrored.** Don't reproduce the CommonMark spec here — link to it.
- **No agentic infrastructure.** No `AGENTS.md`, no agent definitions, no build hooks. If a tool needs this repo, it can read these conventions and the gradient.

## Templates and supporting tooling

- `templates/note.md` — minimal note starter
- `templates/frontmatter/` — example frontmatter for capture and work zones
- `.claude/skills/knowledge-curator/SKILL.md` — gradient-placement guidance for Claude when working in this repo (not coupled to any hook system; the skill is a pure conversational guide here)

## Obsidian

This repo doubles as an Obsidian vault. Minimal config in `.obsidian/` — core plugins plus omnisearch, minimal theme, BRAT, show-hidden-files. Personal workspace state (`workspace*.json`, `cache/`) is gitignored.
