# CLAUDE.md

This file records the operating conventions for this repository. Follow it when creating, editing, or organizing content here.

## Project Positioning

This repository is a publishing base for the owner's personal output. It is scoped to small-scale outputs such as articles. Larger deliverables (e.g. applications) belong in their own separate projects, not in this repository.

## Purpose

This repository exists to help the owner get freelance work under their own name ("ByName"). It serves as the publishing/output base for that goal:

- Content is published in **English** to reach a global audience.
- Content is published in **Japanese** to reach a domestic (Japan) audience.

## Distribution Targets & Language Policy

- **Zenn** is the canonical (source of truth) platform for Japanese content.
- **dev.to** is the canonical (source of truth) platform for English content.
- Japanese and English versions of an article are treated as separate content, not as translations of one another that need a shared canonical. Because of this, no canonical conflict arises between the Japanese and English versions.
- Canonical URL consideration only becomes necessary when the *same-language* article is cross-posted to additional platforms beyond its canonical one (e.g. the same English article posted to more than one English-language platform).
- **Medium is excluded** from distribution targets because it does not support Mermaid diagrams.

## Directory Structure

- Each article gets its own directory.
- The Japanese and English versions of an article live together in the same directory — they are not split into separate language directories.
- Each article directory contains three files: `ja.md`, `en.md`, and `social.md`.
- There is no `assets` directory. Diagrams are managed as Mermaid diagrams embedded in the markdown itself, not as separate image assets, in principle.
- State (draft vs. published) is tracked via a `published` flag in each file's front matter. Files are never moved between draft and published directories — the directory location does not encode publication state.

Example directory tree:

```
articles/
├── my-first-article/
│   ├── ja.md
│   ├── en.md
│   └── social.md
└── another-article-slug/
    ├── ja.md
    ├── en.md
    └── social.md
```

## Per-Article Deliverable Set

Each article directory must contain:

- **`ja.md`** — the article body, written natively in Japanese.
- **`en.md`** — the article body, written natively in English.
- **`social.md`** — social post copy, containing:
  - **X (Twitter)**: separate Japanese and English posts. Each post includes the key points, a link, and 1–2 hashtags.
  - **LinkedIn**: an English-language repost or summary of the article body, plus a link (intended to be placed in a comment rather than the post body), plus 3–5 hashtags.

## Publishing Flow

- There is no automated publishing. Content is manually copy-pasted into each target platform.
- The markdown files in this repository are the single source of truth and are managed centrally here.

## Writing-Language Policy

Public articles that a human reviews are each written as an original in their own language:

- The Japanese version (`ja.md`) is written natively in Japanese.
- The English version (`en.md`) is written natively in English.

Neither version is a translation of the other.

## License

- Article bodies in this repository are licensed under **CC BY 4.0** (see `LICENSE`).
- If this repository comes to contain a significant amount of code snippets in the future, the code portions specifically may be split out and licensed under **MIT** separately. This is a forward-looking note only — no such split exists today.
