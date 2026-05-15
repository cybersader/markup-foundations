---
date created: 2026-05-15
date modified: 2026-05-15
temperature: working
tags:
  - markdoc
  - shortcodes
  - markup-philosophy
aliases:
  - "Markdoc vs shortcodes"
related:
  - "[[keystroke-time-markup-expansion-landscape]]"
  - "[[sources]]"
status: active
---

# Markdoc vs shortcode systems

> [!note] This is a forming opinion
> Position note in `01-working/` — still subject to revision. Pair with [[keystroke-time-markup-expansion-landscape]] for the full taxonomy.

## The core tension

If I'm writing in a markdown space where I want HTML and don't want to do weird stupid crap, I still think **Markdoc** might be one of the best formats — alongside *just letting HTML live inline*. The appeal: structured tag syntax that's first-class in the source, validated by a schema, but still recognizably markdown.

## Why not invent yet another shortcode system

The temptation, especially in SSG-style projects, is to invent a project-specific shortcode vocabulary (`{% callout %}`, `{{< grid >}}`, `:::admonition`, etc.) so authors don't write raw HTML. The problem: **a project-specific shortcode system is yet another abstraction that doesn't durably live over time.** When the SSG changes, when the project gets rewritten, when the build pipeline rots — the shortcode vocabulary rots with it. The source files become bound to a renderer they're not portable away from.

## The alternative: keystroke-time expansion

Rather than inventing a shortcode *system* (build-time or render-time), use a **snippet expansion / keystroke-time expansion** layer on the editor side. The source file ends up containing the expanded text — plain markdown + plain HTML where needed. No project-specific vocabulary lives in the source. The expansion happens at write-time; the artifact on disk is durable across renderers.

This sits at **Layer 1** of the landscape (see [[keystroke-time-markup-expansion-landscape]]) — Emmet, LaTeX Suite, snippetleaf-style engines, system-wide expanders like Espanso.

## Markdoc's role in this view

Markdoc occupies an interesting middle ground:

- Its `{% tag %}` syntax IS a project-specific vocabulary in some sense...
- ...but Markdoc is a *spec* with a schema and a published parser, not a project-local invention.
- So portability comes from "Markdoc the format" being a thing, rather than from each project re-inventing wheels.

For pure source-of-truth durability, **plain markdown + plain HTML + keystroke-time snippet expansion** wins. For *structured* embedded markup that needs schema validation and clean rendering, Markdoc is the cleanest option I've seen.

## Open questions

- How does Markdoc handle author-side ergonomics (do you really want to type `{% callout type="warning" %}...{% /callout %}` raw)?
- Where does Markdoc's tag vocabulary stop being "the spec" and start being project-local invention (custom tags via the schema)?
- For embedded *interactive* content (charts, components), Markdoc vs MDX vs Astro components — Markdoc forces structure, MDX forces JavaScript dependency. Pick your poison.

## Next step

Once these answers settle, this note either:
- Distills into one or more `[[02-learnings/]]` entries on the principle ("source-of-truth durability beats author-side ergonomics for long-lived content")
- Or matures into a `[[03-reference/]]` survey on "embedded-markup formats compared"
