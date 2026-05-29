# Sens Papers — Glossary for Public Writing

> **Purpose**: 公開出版物 (essays/ / papers/ / technical/) の用語安定性確保と、
> arXiv / web 公開時の canonical citation point として機能する用語予約簿。
>
> **Sync model**: **C — 定義同期 / ステータス独立** (2026-05-29 ecri 承認、
> MM-P1-sub)。Stories `meta/glossary.md` と定義レベルは ecri 仲介で同期、
> ステータス (active / reserved / research-watch) は各環境の公開フェーズに応じて
> 独立に管理する。
>
> **Confidentiality**: **public-safe な用語定義のみ**。実装内部、訓練データ、
> 内部研究資料、未公開コードネームのコンテキスト、内部メトリクスは含めない
> (CLAUDE.md §3 / OPERATING.md と整合)。

## Status legend

| status | 意味 |
|---|---|
| `active` | 現在公開可能、essays/ / papers/ / technical/ で使用可、citation 可 |
| `reserved` | 用語予約、Phase 4+ で起草対象。drafts/ では暫定使用可、公開ファイルへの promote は status を `active` に変更後 |
| `research-watch` | 関連研究を継続観測中。起草着手のタイミングは未定 |

---

## 1. モダリティ射程用語 (Sens Modality Scope)

### Sens Text  `active`

テキストモダリティを対象とする Sens の射程。現在の essays/ / papers/ / technical/
は原則として Sens Text の射程内で起草される。Sens プロジェクトの公開発信は
2026-05 時点でこの射程を中核に展開している。

### Sens Audio  `reserved (Phase 4+)`

音声モダリティを対象とする Sens の射程。将来の audio paper / technical
deep-dive の起草対象として用語を予約。Phase 4 以降に着手見込み。

### Sens Image  `reserved (Phase 4+)`

画像モダリティを対象とする Sens の射程。将来の vision paper / technical
deep-dive の起草対象として用語を予約。Phase 4 以降に着手見込み。

### Sens Color  `reserved (Phase 4+)`

色覚 / 色彩特性を対象とする Sens の射程。Sens Image の subset として位置づけ
られる可能性あり (将来定義時に整理)。

### Sens Taste  `reserved (Phase 4+)`

味覚モダリティを対象とする Sens の射程。哲学エッセイ・現象学系 paper での
モダリティ多様性議論の対象として予約。

### Sens Composite  `reserved (Phase 4+)`

複数モダリティの合成・統合を対象とする Sens の射程。モダリティ非依存 Feature
仮説 (下記) の経験的検証 paper の主要射程。Phase 4 以降。

---

## 2. アーキテクチャ用語 (多モダリティ拡張)

### モダリティ固有 SAE  `reserved (Phase 4+)`

特定のモダリティ (テキスト / 音声 / 画像 等) に固有の Sparse Autoencoder。
technical/ 配下の将来 deep-dive paper の対象。実装レベルの詳細は Dev 環境管轄、
Papers では public-safe な抽象レベル (アーキテクチャ概念図、文献的位置づけ)
までを扱う。

### モダリティ非依存 Feature  `reserved (Phase 4+)`

モダリティ表現 (テキスト/音声/画像) の差異を越えて不変な意味的特徴。哲学エッセイ
(Manifesto 語彙的支柱との連動候補) および technical paper の対象。
PRH (Platonic Representation Hypothesis) と概念構造が近接 — 両者とも
「表現基底の差異を越えた意味の不変性」を扱う (§3 参照)。

### 共有埋め込み空間  `research-watch`

異モダリティの表現を統合する埋め込み空間。technical/ の研究系 paper の対象。
**PRH 2025 反例** との連動可能性あり (§3、`drafts/_research-and-direction.md`
§C-6 参照)。背景研究を継続観測中、起草タイミングは Q3-extended (a) 体制
判断後に決定。

---

## 3. Papers 固有用語

### Public Multimodal Scope  `reserved` 🆕

**Papers 環境固有用語**。多モダリティ射程拡張の **public 発信における範囲定義**。
具体的に、ある時点における public-safe な多モダリティ言及範囲を指す:

- どのモダリティが `active` (公開可) / `reserved` (予約のみ) / `research-watch`
  (背景研究中) の status を持つか
- 各モダリティについて、どのレベルの抽象度まで公開してよいか (アーキテクチャ
  概念図 / 実装詳細 / 経験的検証結果)
- Manifesto 射程拡張一節、Foundation License 一般化、Dev SAE 実装の進行状態に
  応じて時系列で変化する動的概念

essays/ / papers/ / technical/ の公開判断時、その時点の Public Multimodal Scope
を参照する。本 glossary の status 列が canonical reference。

---

## 4. 同期ポリシー (Sync policy)

2026-05-29 ecri 承認の同期方式 **C** に基づく運用:

### 4.1 定義同期 (Definition sync)

- 用語定義は Stories `meta/glossary.md` と ecri 仲介で共有
- Papers が定義を更新する場合、handover/ に「Glossary update proposal」として
  記載し、ecri が Stories へ反映
- Stories 起源の定義更新は ecri 経由で本 glossary に反映
- 直接書き込みは行わない (Papers は他環境への書き込み権限なし)

### 4.2 ステータス独立 (Status independent)

- 同一用語が Papers と Stories で異なる status を持ち得る
- 例: 「モダリティ非依存 Feature」は Stories では Application Story 用に
  `reserved` でも、Papers では哲学エッセイの公開状況によって異なる status を
  取り得る
- 各環境の **発信フェーズ** に基づき独立に管理する

### 4.3 promote 規律

- drafts/_*.md では `reserved` / `research-watch` 用語の暫定使用可
- essays/ / papers/ / technical/ への promote は、対象用語が **本 glossary で
  `active`** であることを要件とする
- promote 時、本 glossary の Update history (§6) に該当 essay / paper の reference
  を追記する

### 4.4 drift 検知

- Papers thread が cross-env read で Stories glossary を読む際、定義の乖離を
  検出した場合、handover/ に状況メモを作成して ecri に報告
- 半期に一度 (Mission Control 経由) の整合性チェックを推奨

---

## 5. 起源と承認

- **起源 dispatch**: `sens/docs/governance/dispatch/sens-papers/2026-05-29-multimodal-public-writing-scope.md`
  (Dev 代行起草、5 環境拡張独自価値)
- **Papers 判断**: `sens-papers:handover/dispatch-to-dev-2026-05-29-multimodal-response.md`
  (配置 ② 推奨 / 同期方式 C 推奨)
- **ecri 承認**: 2026-05-29 (MM-P1 + MM-P1-sub の Papers 推奨案を採用)

---

## 6. Update history

| date | change | reference |
|---|---|---|
| 2026-05-29 | Initial glossary created. 9 reserved + 1 active (Sens Text) + 1 research-watch (共有埋め込み空間) + 1 Papers 固有 reserved (Public Multimodal Scope) | sens-papers commit (本 commit), 起源 dispatch MM-P1 |
