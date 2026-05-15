# Example: frontmatter for `01-working/` drafts and forming opinions

A starting point. Adapt as needed.

```yaml
---
date created: 2026-01-15
date modified: 2026-01-15
temperature: working
tags:
  - markdoc
  - shortcodes
aliases: []
source:
  - "[[00-inbox/2026-01-10-markdoc-doc-skim]]"   # where this came from
output:
  - "[[02-learnings/2026-XX-XX-todo]]"           # where this might go next
related:
  - "[[keystroke-time-markup-expansion-landscape]]"
status: active                                    # draft | active | review | ready-to-promote
---
```

## Notes on each field

- **`temperature: working`** — matches the folder.
- **`tags`** — plain topic tags, no prefix. Topic-first, not status-first.
- **`source:`** — wikilinks back to inbox captures or external references that fed this draft.
- **`output:`** — forward links to where you expect this to mature (a planned learning or reference). Optional.
- **`status:`** — where this is in its working cycle. When `ready-to-promote`, move the file out of `01-working/` to its final zone.

## Working notes are durable until they aren't

A working note exists because you don't yet have a clean answer. Two healthy endings:

1. **Crystallize:** the note distills into one atomic learning → file goes to `02-learnings/YYYY-MM-DD-topic.md` with `temperature: learnings`.
2. **Survey:** the note grows into a stable landscape doc → file goes to `03-reference/topic.md` with `temperature: reference`.

If a working note sits for weeks with no movement, ask whether the question itself is still alive. If not, archive it.
