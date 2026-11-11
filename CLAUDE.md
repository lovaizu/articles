# `CLAUDE.md`

This file records the operating conventions for this repository. Follow it when creating, editing, or organizing content here.

## Project positioning

This repository is a publishing base for the owner's personal output, and its scope is small-scale outputs such as articles. Larger deliverables, such as applications, belong in their own separate projects, not in this repository.

## Purpose

This repository exists to help the owner get freelance work under their own name ("ByName"). It serves as the publishing/output base for that goal:

- Content is published in **English** to reach a global audience.
- Content is published in **Japanese** to reach a domestic audience in Japan.

## Distribution targets and language policy

- **Zenn** is the canonical distribution platform for Japanese content.
- **dev.to** is the canonical distribution platform for English content.
- Japanese and English versions of an article are treated as separate content, not as translations of one another that need a shared canonical, so no canonical conflict arises between the Japanese and English versions.
- You need to consider canonical URLs only when an article is cross-posted to additional platforms in the *same* language beyond its canonical one: for example, when the same English article is posted to more than one English-language platform.
- **Medium is excluded** from distribution targets because it doesn't support Mermaid diagrams.

## Directory structure

- Each article gets its own directory, named `YYYYMMDD-slug`, which is a date prefix plus a title slug. For example, `20260707-my-first-article`.
- Article directories live directly at the repository root, not nested under an `articles/` subdirectory. The repository itself is already named `articles`, so it uses no extra `articles/` subfolder.
- The Japanese and English versions of an article live together in the same directory, not split into separate language directories.
- Each article directory contains three files: `ja.md`, `en.md`, and `social.md`.
- There is no `assets` directory. In principle, diagrams are managed as Mermaid diagrams embedded in the markdown itself, not as separate image assets.
- A `published` flag in each file's front matter tracks its state: draft or published. Files are never moved between draft and published directories. The directory location doesn't encode publication state.

Example directory tree:

```
(repository root)/
├── 20260707-my-first-article/
│   ├── ja.md
│   ├── en.md
│   └── social.md
└── 20260710-another-article/
    ├── ja.md
    ├── en.md
    └── social.md
```

## Per-article deliverable set

Each article directory must contain:

- **`ja.md`**: the Japanese article body. See Writing-language policy.
- **`en.md`**: the English article body. See Writing-language policy.
- **`social.md`**: social post copy, which contains the following:
  - **X (Twitter)**: separate Japanese and English posts. Each post includes the key points, a link, and 1–2 hashtags.
  - **LinkedIn**: an English-language repost or summary of the article body, a link, and 3–5 hashtags. The link is intended to go in a comment rather than in the post body.

## Publishing flow

- There is no automated publishing. Content is manually copy-pasted into each target platform.
- The markdown files in this repository are the single source of truth and are managed centrally here.

## Writing-language policy

Public articles that a human reviews are each written as an original in their own language:

- The Japanese version (`ja.md`) is written natively in Japanese.
- The English version (`en.md`) is written natively in English.

Neither version is a translation of the other.

## License

- Article bodies in this repository are licensed under **CC BY 4.0** (see `LICENSE`).
- If this repository comes to contain a significant amount of code snippets in the future, the code portions specifically may be split out and licensed under **MIT** separately. This note only looks ahead: no such split exists today.
