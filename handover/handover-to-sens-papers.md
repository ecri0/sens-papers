# Sens Antifragile 戦略 — Sens Papers 環境向けハンドオーバー

新規環境 Sens Papers の thread 立ち上げ用ハンドオーバー。Antifragile ハンドオーバーパッケージの 5 環境拡張として 2026-05-28 採用。

> **配置経緯**: 本文は Dev 起草草稿（`sens/docs/archive/dispatch/sens-papers/2026-05-28-papers-thread-setup-handover.md`）の ecri 採用版本体。Papers thread 立ち上げ時（2026-05-28）に本 repo へ正式配置。

## 背景

Sens プロジェクトはこれまで Manifesto / Sens Stories / Dev / Foundation の 4 環境体制で動いていたが、`ecri0/sens-papers` という独立 repo が **public writing 専門**として既に稼働しており、これを **5 番目の環境 (Sens Papers)** として明示的に位置づける。

Papers は Antifragile 戦略の 5 層構造のうち、いずれの「戦略層」にも直接属さない、**戦略全層の公開発信を担う**横断環境。

## 5 環境体制への移行

| 環境 | 担当 | Antifragile 戦略層 |
|---|---|---|
| Manifesto | 思想・Sens Constitution・哲学的正統性 | 戦略5 |
| Sens Stories | Application Story / Interview | 戦略 全般（間接支援） |
| Dev | 実装・技術仕様・全体統括 | 戦略 1・2・3 |
| Foundation | License / ガバナンス / Sens Certification Authority | 戦略4 |
| **Sens Papers**（新規明示化） | **公開 essays / papers / technical writing** | 戦略 全層の公開発信（横断）|

## 役割

`ecri0/sens-papers`（Private、CC BY 4.0 + MIT、`https://sens-thread.io` で公開）を運営する。**public-safe な writing の起草・推敲・公開判断**を担う。

## 既存資産の継承

リポジトリ構造（既存、2026-05-28 時点）:

```
sens-papers/
├── README.md
├── LICENSE-CC-BY-4.0       # papers/essays/technical の prose
├── LICENSE-MIT             # scripts/ のコード
├── docs/OPERATING.md       # 既存運用規律（public-only、機密禁止）
├── drafts/                 # WIP（unreviewed、not for citation）
│   ├── _essay-reconciliation.md
│   ├── _manifesto-core.md
│   ├── _research-and-direction.md
│   └── _review-packet.md
├── essays/                 # 公開済 long-form（EW-001 unpublish 後、現在は空）
├── papers/                 # 公開済 arXiv-bound（現在は空）
├── technical/              # 公開済 deep-dives（現在は空）
├── scripts/                # 補助スクリプト（MIT）
└── site/                   # 公開サイト素材
```

物理配置（2026-05-28 sibling 統一）: `/Users/ecri/.claude-worktrees/sens/sens-papers/`

## 既存ルール（OPERATING.md 準拠、必須）

Contributors MUST NOT include:
- Unreleased internal roadmap, timelines, or planning detail
- Any cost, budget, pricing, or economics figures
- Infrastructure internals, deployment topology, or operational tooling
- Hardware procurement decisions
- Unpublished experiment specifics or internal metrics
- Anything not already publicly stated by the project

→ **Dev `CLAUDE.md` confidentiality boundary と完全整合**。違反した内容を public に出すことは絶対禁止。

## Lifecycle

```
Draft thread / Manifesto thread / Dev thread 等から WIP 受領
    ↓
drafts/_<topic>.md として保存（unreviewed marker）
    ↓
推敲（Papers thread）+ confidentiality check
    ↓
ecri レビュー
    ↓
essays/ / papers/ / technical/ へ promote（publish）
    ↓
site/ に反映、必要なら arXiv 投稿
    ↓
（withdraw 必要時）revert commit + index 更新（EW-001 経緯参照）
```

## 4 環境との関係

| from / to | Papers が受け取るもの | Papers が出すもの |
|---|---|---|
| Manifesto | Constitution の公開部分、思想素材 | 哲学エッセイの推敲 |
| Sens Stories | 公開可能な Story 抜粋（人物 archetype レベルまで）| - |
| Dev | public-safe な技術仕様素材（USID 概念、戦略1〜3 の説明）| technical deep-dive |
| Foundation | License / SCA / Foundation 計画の公開部分 | governance 解説 |

直接書き込みは行わない。情報は ecri 経由 or Dev `dispatch/sens-papers/` 経由で来る。

## 参照ルール（5 環境拡張版）

| アクション | Manifesto | Sens Stories | Dev | Foundation | **Sens Papers** |
|---|---|---|---|---|---|
| 自環境を読む | ✓ | ✓ | ✓ | ✓ | ✓ |
| 自環境に書く | ✓ | ✓ | ✓ | ✓ | ✓ |
| 他環境を読む | ─ | Manifesto, Dev | **全環境**（統括）| Dev | **全環境**（公開素材抽出のため）|
| 他環境に書く | ─ | ✗ | ✗（統括メモのみ）| ✗ | **✗** |

Papers は **公開発信のため全環境を読める**が、書き込みは自環境内のみ。

## 短期作業（2-4 週）

### Phase 0: 立ち上げ
1. 本ハンドオーバーを repo に配置（`handover/handover-to-sens-papers.md`）
2. `CLAUDE.md` を repo root に配置
3. session sanity check 規約導入
4. 現状確認 + 未 commit / 未公開状態の把握

### Phase 1: drafts/ レビュー
- `_essay-reconciliation.md` / `_manifesto-core.md` / `_research-and-direction.md` / `_review-packet.md` の状態確認
- ecri レビュー希望のものは review に進める
- WIP のままのものはステータス明示

### Phase 2: EW-001 後続
- EW-001 unpublish 後の修正版（draft thread から流れる可能性）の受領準備
- 公開 / withdraw lifecycle の整備

## あなたに期待しないこと

### Constitution / Manifesto / Anchor の起草
これらは Manifesto 環境の担当。Papers は公開可能な抜粋・引用までを担う。

### Application Story / Interview の起草
これらは Sens Stories 環境の担当。

### 技術仕様の起草
Dev 環境の担当。Papers は public-safe な technical deep-dive の起草まで。

### License / SCA の起草
Foundation 環境の担当。

### 内部情報の公開判断
公開可否の最終判断は常に ecri。

## 判断基準（迷った時の優先順位）

1. **Confidentiality boundary 厳守**（OPERATING.md + Dev CLAUDE.md と整合）
2. **public-safe 検証**（ecri レビュー前に self-check）
3. **citation 可能性**（drafts/ は明示的に「not for citation」マーカー）
4. **Manifesto Constitution との整合**（公開エッセイが Constitution 条文と矛盾しないか）
5. **長期の正統性**（撤回より、最初から公開しない方が安全）

## 確認事項（Papers thread → ecri）

立ち上げ後に ecri 確認:
1. drafts/ 4 件の最新ステータス（draft thread の現況）
2. EW-001 修正版の起草スケジュール
3. arXiv 投稿の計画
4. Papers thread 起動頻度（週次 / 必要時のみ）
