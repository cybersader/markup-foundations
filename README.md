# markup-foundations

A knowledge workspace on the **first principles of markup for content authoring** — markdown, Markdoc, MDX, HTML-in-markdown, shortcode systems, keystroke-time expansion, SSG authoring stacks, and the lineage that connects them.

This is **not an agentic project**. It is a personal reference vault: durable notes on how markup-for-authoring actually works, what tradeoffs the various systems make, and what survives at the source-of-truth layer over time.

## How it's organized

Content lives in `knowledge-base/` and uses a **temperature gradient** — five numbered zones from hot (raw capture) to cold (archived reference). New material lands in `00-inbox/` and matures toward `04-archive/`.

See `knowledge-base/README.md` for the gradient spec and `CLAUDE.md` for repo conventions.

## Scope

Roughly: anything in the path from **keystroke → rendered output** for authored prose, slides, docs, and notes. Markdown core (CommonMark, GFM, OFM), embedded-markup formats (Markdoc, MDX, Quarto), expansion systems (Emmet, snippet engines, Espanso, system-wide expanders, LSP-driven completion), SSG shortcode dialects (Hugo, Eleventy, Astro, Jekyll Liquid, Pandoc, MyST, RST), HTML-in-markdown patterns, and editor-side authoring infrastructure (Obsidian, VS Code, Zed, JetBrains).

Out of scope: full HTML/CSS specs, language-server protocol implementation, general programming docs. Link out to authoritative references instead of mirroring them here.

## Related

Conventions for this repo (temperature gradient, frontmatter, knowledge-curator skill) are borrowed from the sibling [`cybersader-agentic-workflow-and-tech-stack`](https://github.com/cybersader/cybersader-agentic-workflow-and-tech-stack) scaffold so the same patterns and tooling carry over.
