# Example: frontmatter for `00-inbox/` captures

A starting point. Adapt to whatever your capture needs.

```yaml
---
date created: 2026-01-15
date modified: 2026-01-15
temperature: inbox
tags:
  - -capture
  - -clip/article          # or -clip/video, -clip/conversation, etc.
aliases: []
source: https://example.com/article
related: []
status: inbox              # inbox | processing | processed
---
```

## Notes on each field

- **`temperature: inbox`** — tells the curator skill (and you) where this lives. Matches the folder.
- **`-capture`** — optional tag prefix for inbox content. Lets you filter "everything captured but not yet processed."
- **`-clip/<source>`** — optional tag for the source type (article, video, conversation, screenshot).
- **`source:`** — where it came from. URL, conversation participant, book title, etc.
- **`status:`** — progression within the inbox. `inbox` → `processing` (when you're working on it) → `processed` (ready to promote out).

## Variants

- **Conversation captures:** drop `-clip/*`, add `participants: []`.
- **Screenshot dumps:** add `image: "[[attachment.png]]"`.
- **Web clips with quote:** add a `>` callout block with the verbatim quote and a `note:` field with your reaction.

The schema is a suggestion, not a contract. Inbox is a graveyard if you over-engineer the frontmatter — keep it light.
