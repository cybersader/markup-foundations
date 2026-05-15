---
temperature: archive
---

# Archive (Frozen Zone)

Long-term filed knowledge — the natural endpoint for fully-processed content.

**What goes here:**
- Superseded learnings or reference docs that history might want
- Completed survey docs no longer actively consulted
- Old task plans (if you ever create them) with date-prefixed names
- Anything that's "done" and categorized

## How to file (simplest first)

Drop the file in `04-archive/` with a date prefix:

```
04-archive/
├── 2026-03-15-superseded-keystroke-expansion-survey.md
└── 2026-04-02-old-markdoc-position.md
```

That's it. Loose date-prefixed files work great for most things.

## Johnny Decimal (when content accumulates)

Once the archive starts to feel cluttered, adopt Johnny Decimal areas. **Starter areas for the markup-foundations domain** (start with 2-3, add as needed):

```
04-archive/
├── 10-19 Syntax & Spec/
│   ├── 11 Markdown Core/            # CommonMark, GFM, OFM, dialects
│   ├── 12 Embedded Markup/          # Markdoc, MDX, Quarto, MyST
│   └── 13 Adjacent Specs/           # RST, AsciiDoc, Pandoc divs
├── 20-29 Engines & Toolchains/
│   ├── 21 Parsers & Renderers/      # remark, marked, markdown-it
│   ├── 22 Static Site Generators/   # Hugo, Eleventy, Astro, Jekyll
│   └── 23 Document Pipelines/       # Quarto, Pandoc workflows
└── 30-39 Expansion & Templating/
    ├── 31 Keystroke-Time/           # Emmet, snippet engines, LaTeX Suite
    ├── 32 System-Wide Expanders/    # Espanso, TextExpander
    └── 33 Build-Time Shortcodes/    # Hugo shortcodes, Liquid, MDX components
```

### How to file with JD

1. **Pick the area** (10-19, 20-29, etc.) that matches the domain
2. **Pick or create a category** (11, 12, etc.) within that area
3. **Assign an ID** (11.01, 11.02) to the specific item
4. **No area fits?** Loose at `04-archive/` root is fine. Categorize later or leave it.

> [!tip] Start small
> Don't pre-create JD areas you might not need. Loose files are fine until the archive feels cluttered enough that finding things is harder than browsing categories.

## Cross-temperature references

Archive content can be linked FROM any zone:

```markdown
<!-- In 01-working/draft.md -->
This supersedes [[2026-03-15-superseded-keystroke-expansion-survey]].
```

The gradient determines where content LIVES. Wikilinks connect content freely across zones.
