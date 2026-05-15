---
date created: 2026-05-15
date modified: 2026-05-15
temperature: reference
tags:
  - markup-philosophy
  - expansion
  - editor-tooling
  - landscape-survey
aliases:
  - "Keystroke-time expansion landscape"
  - "Markup expansion landscape"
related:
  - "[[markdoc-vs-shortcode-systems]]"
  - "[[sources]]"
---

# Keystroke-time markup expansion: the landscape

> [!abstract] One-sentence synthesis
> The space is fragmented across abbreviation engines (Emmet), editor snippet systems (TextMate syntax), system-wide expanders (Espanso), build-time shortcode parsers (Hugo / Pandoc / MDX), and LLM-augmented completion (Cursor / Tabby) — with no unified standard for the keystroke-time pattern across markup formats and editors. The wedge for a unified project here would be: **the unified, open, local-first keystroke-time expansion layer for markup authoring.**

## Naming the problem

Candidate names for the project umbrella:

- **Keystroke-time markup expansion** — most precise (default)
- Author-time snippet expansion — distinguishes from build/render-time
- Inline abbreviation engines — emphasizes the editor-side
- Markup hydration — the markup → richer-markup transformation
- Live snippet engines

## The four expansion timings (key conceptual frame)

The whole landscape splits cleanly on **when** the expansion happens:

1. **Keystroke-time** (in-editor; source file ends up with the expanded text) → Emmet, snippet engines.
2. **Save-time** (a watcher rewrites the file on save) → niche, e.g. some pre-commit hooks.
3. **Build-time** (compiler / SSG expands shortcodes during render) → Hugo, Eleventy, Quarto, MDX.
4. **Render-time** (runtime parses shortcodes when the user views it) → Slides Extended, reveal.js plugins.

This vault's interest is **#1** — the source-of-truth file contains the expansion, no parser needed downstream.

---

## Layer 1 — abbreviation engines (the Emmet model)

The canonical "type shorthand → press Tab → file has full markup" pattern.

- [Emmet](https://emmet.io/) ([docs](https://docs.emmet.io/), [GitHub](https://github.com/emmetio/emmet)) — the original. Default in VS Code, JetBrains, Zed, Sublime. Has extension JSON for custom snippets.
- [Snippetleaf](https://github.com/artisticat1/snippetleaf) — LaTeX Suite's engine ported to plain CodeMirror; the closest open-source reference for building a CM6-native expansion engine.

## Layer 2 — editor-native snippet systems

Every modern editor has a built-in snippet engine. They mostly share the [TextMate snippet syntax](https://macromates.com/manual/en/snippets) (`${1:placeholder}` tab stops) which became a de facto standard.

- **VS Code snippets** — [docs](https://code.visualstudio.com/docs/editor/userdefinedsnippets), `.code-snippets` files, project-scoped supported.
- **JetBrains Live Templates** — [docs](https://www.jetbrains.com/help/idea/using-live-templates.html); most powerful (parameterized, predefined functions, contexts).
- **Sublime Text snippets** — [docs](https://www.sublimetext.com/docs/completions.html), `.sublime-snippet` files.
- **Neovim:**
  - [LuaSnip](https://github.com/L3MON4D3/LuaSnip) — modern, Lua-based.
  - [UltiSnips](https://github.com/SirVer/ultisnips) — Python-based, classic.
  - [vim-snippets](https://github.com/honza/vim-snippets) — huge community library covering ~150 filetypes.
- **Zed** — snippets via `keymap.json` and [Emmet built-in](https://zed.dev/languages/emmet).
- **Helix** — has snippet support via LSP, no native engine.

[LSP snippet protocol](https://microsoft.github.io/language-server-protocol/specifications/lsp/3.17/specification/#textDocument_completion) — `completionItem.snippet` is the standard way LSPs return expansions. Means if you write a language server, every editor gets snippet support for free.

## Layer 3 — system-wide text expanders

Application-agnostic; work in any text field including Obsidian, browsers, Slack.

- [Espanso](https://espanso.org/) ([GitHub](https://github.com/espanso/espanso), [hub](https://hub.espanso.org/)) — free, open-source, Rust, YAML config, cross-platform including Linux.
- [TextExpander](https://textexpander.com/) — paid, polished GUI, teams.
- [aText](https://www.trankynam.com/atext/) — one-time-purchase, lighter.
- [Beeftext](https://github.com/xmichelo/Beeftext) — Windows-only, free, GUI.
- [AutoHotkey](https://www.autohotkey.com/) — Windows scripting, has hotstring / expansion support.
- [Hammerspoon](https://www.hammerspoon.org/) — macOS Lua scripting, can do expansion via [TextExpansion module](https://github.com/scottwhudson/TextExpansion).

## Layer 4 — Obsidian-specific

For Obsidian-resident authoring.

- [LaTeX Suite](https://github.com/artisticat1/obsidian-latex-suite) ([docs](https://github.com/artisticat1/obsidian-latex-suite/blob/main/DOCS.md), [DeepWiki](https://deepwiki.com/artisticat1/obsidian-latex-suite)) — gold standard for fast keystroke expansion. Despite the name, the engine is general; you can use any snippets, not just LaTeX.
- [Text Snippets](https://github.com/Maxwell-Liu/obsidian-text-snippets) — straightforward snippet plugin.
- [Text Expander JS](https://github.com/migzone/obsidian-text-expander-js) — JS-driven (dynamic snippets).
- [Templater](https://github.com/SilentVoid13/Templater) — full templating language (JS-based), hotkey / text-trigger expansion.
- [Various Complements](https://github.com/tadashi-aikawa/obsidian-various-complements-plugin) — suggestion-style autocomplete.
- [Obsidian Abbreviations](https://github.com/WoodenMaiden/obsidian-abbreviations) — word-boundary expansion.
- [QuickAdd](https://github.com/chhoumann/quickadd) — template insertion with prompts.

## Layer 5 — static site generator shortcodes (build-time, not the target, but related)

The ancestors of the design. Worth knowing the lineage.

- [Hugo shortcodes](https://gohugo.io/content-management/shortcodes/) — `{{< name args >}}`, the modern gold standard for build-time expansion.
- [Jekyll Liquid](https://jekyllrb.com/docs/liquid/) — `{% include %}`, `{% raw %}`, etc.
- [Eleventy shortcodes](https://www.11ty.dev/docs/shortcodes/) — JS functions invoked from templates.
- [Astro components](https://docs.astro.build/en/core-concepts/astro-components/) in markdown — `.mdx`-style component embedding.
- [Markdoc](https://markdoc.dev/) — Stripe's structured markdown with `{% callout %}` syntax.
- [MDX](https://mdxjs.com/) — markdown + JSX; build-time compilation.
- [MyST](https://myst-parser.readthedocs.io/) — markdown for Sphinx; `{directive}` syntax.
- [Quarto shortcodes](https://quarto.org/docs/extensions/shortcodes.html) — `{{< shortcode >}}` Hugo-style for Quarto.
- [Pandoc divs/spans](https://pandoc.org/MANUAL.html#divs-and-spans) — `::: name` and `[text]{.class}`; widely adopted.
- [reStructuredText directives](https://docutils.sourceforge.io/docs/ref/rst/directives.html) — `.. directive::`; the OG of "shortcode in markup."

These show what shortcode vocabularies look like at scale.

## Layer 6 — LLM-augmented expansion

The 2026 layer. Trades determinism for flexibility.

- [Cursor](https://cursor.com/) — `.cursorrules` files describe shortcode vocab; Cursor's inline completion expands intent.
- [GitHub Copilot](https://github.com/features/copilot) — custom instructions for the same pattern.
- [Continue.dev](https://continue.dev/) ([GitHub](https://github.com/continuedev/continue)) — open-source Cursor alternative; supports local models.
- [Codeium](https://codeium.com/) / [Windsurf](https://codeium.com/windsurf) — free tier, AI completions.
- [Cody](https://sourcegraph.com/cody) by Sourcegraph — open-source.
- [Tabby](https://github.com/TabbyML/tabby) — self-hosted, open-source AI coding assistant. Local-first, no commercial-model dependency.
- [FauxPilot](https://github.com/fauxpilot/fauxpilot) — older OSS Copilot alternative.
- Claude Code skills ([`mattpocock/skills` pattern](https://github.com/mattpocock/skills)) — describe vocabulary in SKILL.md; agent uses it.
- [Obsidian Companion](https://github.com/rizerphe/obsidian-companion) — AI inline autocomplete inside Obsidian; can target local Ollama.
- [Obsidian Copilot](https://github.com/logancyang/obsidian-copilot) by Logan Yang — chat + completion; Ollama-native.

## Layer 7 — local LLM runtimes (the engine for layer 6)

For LLM expansion that stays local-only / open-source-model:

- [Ollama](https://ollama.com/) ([GitHub](https://github.com/ollama/ollama)) — the de facto standard. `localhost:11434`, OpenAI-compatible API. Models: [Qwen 2.5 Coder](https://ollama.com/library/qwen2.5-coder) (recommended), [Llama 3.2](https://ollama.com/library/llama3.2), [Gemma 2](https://ollama.com/library/gemma2).
- [LM Studio](https://lmstudio.ai/) — GUI, same API as Ollama.
- [llama.cpp](https://github.com/ggerganov/llama.cpp) — the underlying inference engine; can run standalone.
- [WebLLM](https://github.com/mlc-ai/web-llm) — runs models in the browser / Electron via WebGPU; zero external dependency.
- [Transformers.js](https://github.com/xenova/transformers.js) — Hugging Face's browser-side ONNX inference; smaller models (≤1B realistic).
- [MLX](https://github.com/ml-explore/mlx) — Apple Silicon-native; very fast on M-series Macs.
- [vLLM](https://github.com/vllm-project/vllm) — heavyweight, batch-serving; overkill for personal use.

---

## Underlying tech worth bookmarking

- [CodeMirror 6 autocomplete](https://codemirror.net/docs/ref/#autocomplete) ([npm](https://www.npmjs.com/package/@codemirror/autocomplete), [example](https://codemirror.net/examples/autocompletion/)) — modern editor's built-in snippet / completion engine. What Obsidian uses.
- [Monaco snippets](https://github.com/microsoft/monaco-editor/blob/main/docs/integrate-amd-cross.md) — VS Code's editor for web; same TextMate snippet syntax.
- [Tree-sitter](https://tree-sitter.github.io/) — incremental parser; useful for context-aware expansion ("only expand grid in markdown body, not inside code fences").
- [textmate-grammars](https://github.com/textmate/textmate) — the grammar definition format that drives syntax highlighting + context detection in most editors.

## Open-source reference implementations worth reading

For building in this space, codebases to study:

- [LaTeX Suite](https://github.com/artisticat1/obsidian-latex-suite) — fast Obsidian keystroke expansion (CM6-based).
- [Snippetleaf](https://github.com/artisticat1/snippetleaf) — same engine, decoupled from Obsidian (pure CM6).
- [Espanso core](https://github.com/espanso/espanso) — Rust system-wide expander; clean architecture for triggers + matchers + extensions.
- [Emmet](https://github.com/emmetio/emmet) — abbreviation parser; non-trivial but small enough to study.
- [Tabby](https://github.com/TabbyML/tabby) — local AI completion server; reference for the LLM-augmented layer.
- [Obsidian Companion](https://github.com/rizerphe/obsidian-companion) — example of integrating local LLM into Obsidian completion.
