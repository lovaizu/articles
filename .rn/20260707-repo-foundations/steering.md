Rn version: 0.8.0

# Goal

記事アウトプット用リポジトリ（lovaizu/articles）に LICENSE（CC BY 4.0 の公式全文）と CLAUDE.md（プロジェクト運営方針）を新規作成する。CLAUDE.md には、プロジェクトの位置づけ・目的・配信先と言語・ディレクトリ構成・成果物セット・公開フロー・執筆言語の方針を記載し、将来コードスニペットが増えた場合はコード部分のみ MIT ライセンスに分離する可能性がある旨を注記する。

# Acceptance criteria

- LICENSE ファイルがリポジトリルートに存在し、Creative Commons Attribution 4.0 International (CC BY 4.0) の公式全文（Legal Code）がそのまま収録されている（要約や改変ではなく原文）。
- CLAUDE.md がリポジトリルートに存在し、以下をすべて含む：
  - プロジェクトの位置づけ（自分の作品をアウトプットするプロジェクトであり、アプリ等の大きな成果物は別プロジェクトとし、記事など小規模なアウトプットはこのリポジトリで扱う旨）
  - 目的（フリーランスとして ByName で仕事を得るための発信基盤であり、英語で世界に・日本語で国内に発信する旨）
  - 配信先と言語の方針（Zenn=日本語の正本、dev.to=英語の正本、日英は別コンテンツのため canonical 競合が生じない旨、同一言語記事の複数箇所転載時のみ canonical 考慮が必要な旨、Medium は Mermaid 非対応のため配信先から除外する旨）
  - ディレクトリ構成の規約（記事ごとにディレクトリを切り日英を同じディレクトリに置くこと、各記事ディレクトリに ja.md / en.md / social.md を格納すること、その例、assets ディレクトリを作らず図は原則 Mermaid で管理すること、状態管理は front matter の published フラグで行い draft/published のディレクトリ移動はしないこと）
  - 記事1本ごとに揃える成果物セット（本文 ja.md/en.md、SNS投稿文 social.md の内訳：X 日英それぞれの要点＋リンク＋ハッシュタグ1〜2個、LinkedIn 英語の本文転載または要約＋リンクはコメント欄想定＋ハッシュタグ3〜5個）
  - 公開フロー（自動公開は行わず各プラットフォームへ手動で貼り付ける旨、md を正本として一元管理する旨）
  - 執筆言語の方針（人間がレビューする公開記事は日本語版=日本語、英語版=英語でそれぞれオリジナルとして執筆する旨）
  - ライセンスに関する注記（記事本文は CC BY 4.0 対象であり、将来コードスニペットを多く含む場合はコード部分のみ MIT ライセンスに分離する可能性がある旨）
- CLAUDE.md は英語で記述されている。
- LICENSE / CLAUDE.md の内容が、ユーザーが指定した方針をすべて反映しており、指定されていない方針を新たに追加していない（スコープの逸脱がない）。
- 変更がブランチにコミットされ、リモートに push されている。
- セッションの draft PR がオープンされ、steering.md へのリンクのみを本文に持つ。

# Assumptions

- 対象リポジトリは origin=https://github.com/lovaizu/articles.git、現状 README.md のみのリポジトリであり、これが「作成済みの記事アウトプット用リポジトリ」である（確認済み：リモートと内容から明らか）。
- LICENSE ファイルはリポジトリルートに拡張子なしの `LICENSE` として配置する（GitHub の自動認識規約に合わせる一般的な慣習）。
- CC BY 4.0 の公式全文（英語 Legal Code）は creativecommons.org の正式配布文を用いる。日本語訳は補助的にも併記しない — LICENSE ファイルは公式全文のみとする（ユーザー指示「公式全文を配置」に従う）。
- CLAUDE.md の記述言語は英語（ユーザー確認済み）。
- design.md は作成しない — 今回の作業はユーザーが既に確定した方針をそのままドキュメント化するものであり、独自の構造上の意思決定を伴わないため。design ゲートはプランゲートに畳み込む。

# Rules

- commit and push every change; one completion marker per task
- LICENSE は CC BY 4.0 の公式全文を一字一句改変せずに収録する
- CLAUDE.md は英語で記述する
- 未確定点があれば推測せず、ユーザーに確認する
- 実物ベース（実際のリポジトリ構成・実在するファイル）で進める

# Tasks

### #1: Create LICENSE with the official CC BY 4.0 legal code

**Purpose**: Add the official, unmodified CC BY 4.0 (Creative Commons Attribution 4.0 International) legal code as `LICENSE` at repo root.

**Prerequisites**: none

**Steps**:

- [ ] Fetch the official CC BY 4.0 legal code text from creativecommons.org
- [ ] Write it verbatim to `LICENSE` at repo root
- [ ] self-check (OK/NG per completion criterion, record in checks/1.md)
- [ ] QA expert review (subagent)
- [ ] Craft expert review (subagent, per the task's medium — legal/writing text)
- [ ] Verification expert review (subagent, per the task's medium)

**Completion criteria**:

- `LICENSE` at repo root contains the complete, unmodified CC BY 4.0 International legal code, matching the official creativecommons.org text exactly (no summary, no paraphrase, no omitted sections)
- No unrelated content (other licenses, commentary) is present in the file

### #2: Create CLAUDE.md documenting the repository's operating policy

**Purpose**: Author `CLAUDE.md` at repo root in English, capturing every policy point specified by the user (positioning, purpose, distribution targets & languages, directory structure, per-article deliverable set, publishing flow, writing-language policy, and the CC BY 4.0 / future-MIT-for-code note).

**Prerequisites**: none

**Steps**:

- [ ] Draft `CLAUDE.md` covering: project positioning, purpose, distribution & language policy, directory structure (with the example tree), per-article deliverable set (ja.md/en.md/social.md incl. X/LinkedIn conventions), publishing flow, writing-language policy, and the license note (articles under CC BY 4.0; future code-heavy split to MIT noted)
- [ ] Cross-check every bullet against the user's original policy list in the session goal to ensure nothing is dropped or invented
- [ ] self-check (OK/NG per completion criterion, record in checks/2.md)
- [ ] QA expert review (subagent)
- [ ] Craft expert review (subagent, per the task's medium — writing)
- [ ] Verification expert review (subagent, per the task's medium)

**Completion criteria**:

- `CLAUDE.md` exists at repo root, written in English, and every policy point listed in the Goal/Acceptance criteria is present and accurately represented
- No policy is invented or altered beyond what the user specified

### #3: Evaluation sign-off

**Purpose**: Present the finished LICENSE + CLAUDE.md against the Acceptance criteria for the user's verdict.

**Prerequisites**: #1, #2

**Steps**:

- [ ] Present the Acceptance criteria run result to the user
- [ ] Take the verdict via /rn:ty (approve) or /rn:gm (revise → address the feedback, re-present)

**Completion criteria**:

- The Acceptance criteria run is approved by the user

# State

- **Status**: paused
- **Date**: 2026-07-07
- **Last completed**: (none yet)
- **Next**: plan-gate approval (`/rn:ty` or `/rn:gm`), then #1 Create LICENSE with the official CC BY 4.0 legal code
- **Notes**: Branch `repo-foundations` committed locally but not pushed — `git push -u origin repo-foundations` failed with `403 Permission denied to kiyobot` on `https://github.com/lovaizu/articles.git` (gh auth is otherwise valid). No draft PR exists yet. Open question posed to user, unanswered: grant `kiyobot` write access to `lovaizu/articles`, push under a different account, or proceed without a PR (local commits only)? Once resolved, push the branch, open the draft PR, then take the plan-gate sign-off before starting #1.
