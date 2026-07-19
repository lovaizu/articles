Rn version: 0.8.0

# Goal

記事アウトプット用リポジトリ（lovaizu/articles）に LICENSE（CC BY 4.0 の公式全文）と CLAUDE.md（プロジェクト運営方針）を新規作成する。CLAUDE.md には、プロジェクトの位置づけ・目的・配信先と言語・ディレクトリ構成・成果物セット・公開フロー・執筆言語の方針を記載し、将来コードスニペットが増えた場合はコード部分のみ MIT ライセンスに分離する可能性がある旨を注記する。

# Acceptance criteria

- LICENSE ファイルがリポジトリルートに存在し、Creative Commons Attribution 4.0 International (CC BY 4.0) の公式全文（Legal Code）がそのまま収録されている（要約や改変ではなく原文）。
- CLAUDE.md がリポジトリルートに存在し、以下をすべて含む：
  - プロジェクトの位置づけ（自分の作品をアウトプットするプロジェクトであり、アプリ等の大きな成果物は別プロジェクトとし、記事など小規模なアウトプットはこのリポジトリで扱う旨）
  - 目的（フリーランスとして ByName で仕事を得るための発信基盤であり、英語で世界に・日本語で国内に発信する旨）
  - 配信先と言語の方針（Zenn=日本語の正本、dev.to=英語の正本、日英は別コンテンツのため canonical 競合が生じない旨、同一言語記事の複数箇所転載時のみ canonical 考慮が必要な旨、Medium は Mermaid 非対応のため配信先から除外する旨）
  - ディレクトリ構成の規約（記事ごとにディレクトリを切り日英を同じディレクトリに置くこと、記事ディレクトリはリポジトリ直下に配置し `articles/` 等のサブディレクトリは作らないこと、ディレクトリ名は `YYYYMMDD-slug` 形式（日付-タイトル）とすること、各記事ディレクトリに ja.md / en.md / social.md を格納すること、その例、assets ディレクトリを作らず図は原則 Mermaid で管理すること、状態管理は front matter の published フラグで行い draft/published のディレクトリ移動はしないこと）
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

### #1: CC BY 4.0 公式全文で LICENSE を作成

**目的**: CC BY 4.0（Creative Commons Attribution 4.0 International）の公式・無改変の法的文書を `LICENSE` としてリポジトリルートに追加する。

**前提**: なし

**手順**:

- [x] creativecommons.org から CC BY 4.0 の公式法的文書テキストを取得
- [x] リポジトリルートの `LICENSE` に一字一句そのまま記載
- [x] self-check（完了基準ごとに OK/NG を判定し checks/1.md に記録）
- [x] QA expert review（サブエージェント）
- [x] Craft expert review（サブエージェント、当該タスクのメディア種別＝法的/文章に応じて）
- [x] Verification expert review（サブエージェント、当該タスクのメディア種別に応じて）

**完了基準**:

- リポジトリルートの `LICENSE` に、CC BY 4.0 International の完全かつ無改変の法的文書が、creativecommons.org の公式テキストと完全一致する形で収録されている（要約・言い換え・省略なし）
- 無関係な内容（他のライセンス、コメント等）がファイル内に存在しない

### #2: リポジトリ運営方針を記載した CLAUDE.md を作成

**目的**: ユーザーが指定した全方針（位置づけ、目的、配信先と言語、ディレクトリ構成、記事ごとの成果物セット、公開フロー、執筆言語の方針、CC BY 4.0／将来のコードMIT分離の注記）を網羅した `CLAUDE.md` を英語でリポジトリルートに作成する。

**前提**: なし

**手順**:

- [x] `CLAUDE.md` の草稿作成：プロジェクトの位置づけ、目的、配信先と言語の方針、ディレクトリ構成（例のツリーを含む）、記事ごとの成果物セット（ja.md/en.md/social.md、X/LinkedInの規約を含む）、公開フロー、執筆言語の方針、ライセンスに関する注記（記事はCC BY 4.0対象、将来コードが多くなった場合はコード部分のみMIT分離の可能性）をカバー
- [x] セッションのGoalにあるユーザーの原方針リストと全項目を照合し、漏れや追加がないことを確認
- [x] self-check（完了基準ごとに OK/NG を判定し checks/2.md に記録）
- [x] QA expert review（サブエージェント）
- [x] Craft expert review（サブエージェント、当該タスクのメディア種別＝文章に応じて）
- [x] Verification expert review（サブエージェント、当該タスクのメディア種別に応じて）

**完了基準**:

- リポジトリルートに `CLAUDE.md` が存在し、英語で記述されており、Goal/Acceptance criteria に列挙された全ての方針項目が正確に反映されている
- ユーザーが指定した範囲を超える方針の創作や改変がない

### #3: 評価サインオフ

**目的**: 完成した LICENSE + CLAUDE.md を Acceptance criteria に照らしてユーザーの判定を仰ぐ。

**前提**: #1, #2

**手順**:

- [x] Acceptance criteria の照合結果をユーザーに提示
- [ ] /rn:ty（承認）または /rn:gm（修正 → フィードバック対応後、再提示）で判定を受け取る

**完了基準**:

- Acceptance criteria の照合結果がユーザーに承認されている

# State

(written by /rn:dn, read and reset to this placeholder by /rn:up. `Status` is `paused` while a
session is suspended — the signal /rn:up and /rn:dn search for — and resets to `not suspended` here,
so only a genuinely suspended session reads `paused`.)

- **Status**: not suspended
- **Date**: YYYY-MM-DD
- **Last completed**: #N description
- **Next**: #N description
- **Notes**: bounded forward pointer — branch/PR, next concrete action, open blockers, user-deferred paths, open questions / pending decisions not yet captured in `design.md`; not a re-narration of the session (that lives in `git log`)
