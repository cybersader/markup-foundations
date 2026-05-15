---
name: knowledge-curator
description: Use PROACTIVELY when creating files, completing tasks, or working in this knowledge-base/ folder. Guides proper use of the temperature gradient system.
---

# Knowledge Curator

You help maintain this knowledge-base using the **temperature gradient** pattern with **5 numbered zones**.

> [!note]
> This repo is a pure knowledge workspace. There are no hooks, no `task_plan.md` automation, no session-end scripts. The skill here is a **pure conversational guide** — it nudges where content should live; it does not assume any tooling beyond the filesystem and Obsidian.

---

## Temperature Gradient (5 Zones)

```
HOT                                                                        COLD
◄──────────────────────────────────────────────────────────────────────────────►

task_plan.md   00-inbox/   01-working/   02-learnings/   03-reference/   04-archive/
     │            │            │              │               │              │
 this action    today      this week     permanent        stable          filed
```

| Zone | Folder | What Goes Here |
|------|--------|----------------|
| **Hot** | `task_plan.md` | Optional — current session focus, if you want one |
| **Warm** | `00-inbox/` | Quick captures, unprocessed notes |
| **Active** | `01-working/` | Drafts, active synthesis, opinions in formation |
| **Cool** | `02-learnings/` | Distilled atomic insights (permanent) |
| **Cold** | `03-reference/` | Stable docs, surveys, guides — actively consulted |
| **Frozen** | `04-archive/` | Long-term filed knowledge (Johnny Decimal optional) |

Numbers show flow direction: content matures from 00 → 04.

### This Is a Gradient, Not a Pipeline

The zones are a **continuous temperature spectrum**, not strict buckets:

- Content **can skip zones** — a clear insight goes straight to `02-learnings/`, skipping `00-inbox/` and `01-working/`
- Content **doesn't have to pass through every zone** — a stable survey goes directly to `03-reference/`
- **Everything eventually flows toward cold** — content either matures or gets archived
- **Direction is always hot → cold** — content cools as it matures, never heats back up
- **Archive (04) is the eventual destination for ALL finished content**

```
Direct paths are fine:

  Raw capture ──────────────→ 00-inbox/     (default)
  Clear insight ────────────→ 02-learnings/ (skip inbox + working)
  Stable doc/survey ────────→ 03-reference/ (skip everything)
  Completed work ───────────→ 04-archive/   (filed)
```

---

## When Creating Files

**ALWAYS ask:** "Where in the gradient should this go?"

| If the content is... | Place in... |
|---------------------|-------------|
| Quick thought, raw capture, link to triage | `00-inbox/` |
| Draft needing work, forming opinion | `01-working/` |
| Finished atomic insight | `02-learnings/` |
| Stable survey, guide, or landscape doc | `03-reference/` |
| Done, needs filing | `04-archive/` (JD area or loose at root) |
| Temporary/scratch | Consider if it's needed at all |

**Default to `00-inbox/`** for uncertain items. Better to capture warm than lose.

---

## When Content Reaches Archive

`04-archive/` is the **natural endpoint** for all finished content. Two acceptable forms:

**Flat archive** (start here):
```
04-archive/
├── 2026-01-15-superseded-survey.md
└── 2026-01-20-old-position-note.md
```

**Johnny Decimal** (when content accumulates):
```
04-archive/
├── 10-19 Syntax & Spec/
│   ├── 11 Markdown Core/
│   └── 12 Embedded Markup/
├── 20-29 Engines & Toolchains/
└── 30-39 Expansion & Templating/
```

Areas for this project's domain are defined in `knowledge-base/04-archive/_README.md`. Start with 2-3 areas; add more as content demands.

---

## Cross-Temperature Linking

Content maturity flows one direction (00→04), but **references go any direction** via wikilinks:

```markdown
<!-- In 01-working/markdoc-vs-shortcode-systems.md -->
See [[keystroke-time-markup-expansion-landscape]] for the full taxonomy.
```

The gradient determines WHERE content lives. Wikilinks connect content freely across zones.

---

## File Format

All knowledge-base files use **Obsidian Flavored Markdown**:

```markdown
---
date created: YYYY-MM-DD
date modified: YYYY-MM-DD
temperature: inbox | working | learnings | reference | archive
tags:
  - topic
related:
  - "[[Other Note]]"
---

## Content

Your content here...

> [!tip] Key Takeaway
> Important points in callouts
```

---

## Gradient Transitions

Content naturally cools over time. Prompt transitions when content sits warmer than it needs to be:

| Situation | Direction | Suggest |
|-----------|-----------|---------|
| Inbox item aged 3+ days | warm → active | "Process to `01-working/` or skip to `02-learnings/`?" |
| Inbox item already clear | warm → cool | "This looks distilled — move directly to `02-learnings/`?" |
| Working doc stable | active → cool/cold | "Ready to move to `02-learnings/` or `03-reference/`?" |
| Reference doc no longer consulted | cold → frozen | "File into `04-archive/`?" |
| Creating file at project root | outside → gradient | "Should this be in `knowledge-base/`?" |
| Any content fully processed | any → frozen | "This is done — archive to `04-archive/`?" |

### The Funneling Principle

Everything flows hot → cold. The question is never "should this cool down?" — it's "how far should it cool?"

- **Inbox items** should not stay in inbox. Process them within a session or two.
- **Working drafts** either mature (promote) or get acknowledged as done (archive).
- **Learnings** are permanent — they stay unless superseded.
- **Reference docs** are actively used — they move to archive when no longer consulted.
- **Archive** is the endpoint. Content rests here. Found via search or links.

---

## Key Principles

1. **It's a gradient, not a pipeline** — content can skip zones, jump directly where it belongs
2. **Everything flows toward cold** — all content eventually cools; the question is how far
3. **Capture liberally** — `00-inbox/` is cheap, lost insights are expensive
4. **Process regularly** — don't let inbox become a graveyard; funnel content down
5. **Distill ruthlessly** — learnings should be atomic and actionable
6. **Link generously** — wikilinks create value through connection across zones
7. **Archive, don't delete** — history has value; `04-archive/` is the natural endpoint
8. **Loose files are fine** — not everything needs JD structure

---

## See Also

- `knowledge-base/README.md` — full gradient spec
- `knowledge-base/04-archive/_README.md` — Johnny Decimal areas for this domain
- `CLAUDE.md` — repo-level conventions
