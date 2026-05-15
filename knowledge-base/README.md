---
date created: 2026-05-15
date modified: 2026-05-15
temperature: reference
---

# Knowledge Base

This vault uses the **temperature gradient** system for knowledge management. Content flows from hot (raw captures) to cold (archived reference) as it matures.

## Gradient Mapping (5 Zones)

```
HOT                                                                        COLD
<------------------------------------------------------------------------------>

task_plan.md   00-inbox/   01-working/   02-learnings/   03-reference/   04-archive/
     |            |            |              |               |              |
 this action    today      this week     permanent        stable          filed
     |            |            |              |               |              |
  "doing"     "captured"  "processing"  "distilled"     "accessed"     "organized"
```

Numbers make flow direction explicit: content matures from 00 → 04.

## Where Things Live

| Zone | Folder | What Goes Here |
|------|--------|----------------|
| **Hot** | `task_plan.md` (root) | Optional session focus — create only for multi-phase work |
| **Warm** | `00-inbox/` | Raw captures, quick notes, unprocessed discoveries |
| **Active** | `01-working/` | Drafts being synthesized, opinions forming, comparisons in progress |
| **Cool** | `02-learnings/` | Distilled atomic insights — one insight per file, dated `YYYY-MM-DD-topic.md` |
| **Cold** | `03-reference/` | Stable surveys, landscape docs, guides, how-tos — actively consulted |
| **Frozen** | `04-archive/` | Long-term filed knowledge (Johnny Decimal optional) |

## This is a gradient, not a pipeline

- Content **can skip zones** — a clear insight can land directly in `02-learnings/`.
- A stable survey doc can land directly in `03-reference/`.
- Flow direction is always hot → cold. Content never heats back up.
- `04-archive/` is the eventual destination for ALL fully-processed content.

## 04-archive: Johnny Decimal (optional)

Start with loose date-prefixed files at the archive root. Adopt Johnny Decimal areas only when content accumulates enough to need them. Areas for this domain are defined in `04-archive/_README.md`.

```
04-archive/
├── 2026-03-15-superseded-survey.md      # Loose is fine
├── 10-19 Syntax & Spec/
│   └── 11 Markdown Core/
└── 20-29 Engines & Toolchains/
```

## Cross-temperature references

Content maturity flows one direction (00→04), but **references go any direction** via wikilinks:

```markdown
<!-- In 01-working/markdoc-vs-shortcode-systems.md -->
See [[keystroke-time-markup-expansion-landscape]] for the full taxonomy.
```

The gradient determines WHERE content lives. Wikilinks connect content freely across zones.

## Usage

1. **Capturing:** Drop new material in `00-inbox/`. Don't think hard about it.
2. **Processing:** When you sit down to work, move inbox items into `01-working/` drafts, or distill them directly to `02-learnings/`.
3. **When insights crystallize:** Write to `02-learnings/YYYY-MM-DD-topic.md`. One insight per file.
4. **When a survey solidifies:** Move to `03-reference/topic.md`.
5. **When something is done:** File into `04-archive/`.

## See Also

- `../CLAUDE.md` — repo conventions
- `../.claude/skills/knowledge-curator/SKILL.md` — gradient-placement guidance
- `04-archive/_README.md` — Johnny Decimal areas for this domain
