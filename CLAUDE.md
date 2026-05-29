# Sens Papers — Project Instructions for Claude

## 1. Project Identity
- Repo: ecri0/sens-papers (Private)
- Role: Sens プロジェクト 5 環境のうち **Sens Papers 環境** —— public-facing
  essays / papers / technical writing の起草・推敲・公開
- 戦略層: Antifragile 戦略の 5 層構造のうち、全層の **公開発信を担う横断環境**
  （いずれの戦略層にも直接属さない）
- Canonical working directory: `/Users/ecri/.claude-worktrees/sens/sens-papers/`
  （Mission Control mirror 対象、sibling 統一 2026-05-28）
- Sibling environments:
  - `/Users/ecri/.claude-worktrees/sens/sens-manifesto/` — Manifesto (戦略 5)
  - `/Users/ecri/.claude-worktrees/sens/sens-stories/` — Application Story
  - `/Users/ecri/.claude-worktrees/sens/sens/` — Dev (戦略 1・2・3、統括)
  - `/Users/ecri/.claude-worktrees/sens/sens-foundation/` — License / SCA (戦略 4)

## 2. Session Start Sanity Check（2026-05-28 規約、R5 dispatch）

session 開始時に最初の Bash で実行:

```bash
pwd
git rev-parse --show-toplevel
git remote -v
git log --oneline -1
```

期待値:
- pwd → `/Users/ecri/.claude-worktrees/sens/sens-papers`
- toplevel → 同上
- remote → `origin https://github.com/ecri0/sens-papers.git`
- log → 直近 commit

乖離検知時:
- `/Users/ecri/.claude-worktrees/sens/sens/docs/governance/dispatch/sens-papers/` 確認
- `/Users/ecri/.claude-worktrees/sens/sens/docs/archive/dispatch/sens-papers/` 確認
- 異常があれば `handover/` に状況メモを残し ecri に報告（§6 参照）

## 3. Confidentiality Boundary（最重要）

`docs/OPERATING.md` に従い、internal-only 情報は絶対公開しない:

Contributors MUST NOT include:
- Unreleased internal roadmap, timelines, or planning detail
- Any cost, budget, pricing, or economics figures
- Infrastructure internals, deployment topology, or operational tooling
- Hardware procurement decisions
- Unpublished experiment specifics or internal metrics
- Anything not already publicly stated by the project

Sens プロジェクト固有の禁止対象:
- 内部ロードマップ / GPU 予算 / KPI / 単価 / Polaris 戦略
- インフラ内部 / Apple Silicon 等の specifics
- 未発表実験詳細 / 内部メトリクス
  - **多モダリティ拡張に伴う追加 (2026-05-29 MM-P3)**:
    - 画像 SAE 訓練データの IP（著作権 / プライバシー、データセット由来情報含む）
    - 音声 SAE 訓練データの IP（同上、話者識別可能性含む）
    - 共有埋め込み空間の研究内部資料（Z アプローチ研究の内部進展、未公開実装メモ、内部ベンチマーク）
- ADR Revert 履歴（ADR-012, ADR-014 等）
- Fragile Triad 制約
- 内部プロダクト/機能のコード名（Prism / Hub / Node 等の **未公開** コンテキスト）
- Manifesto thread の NON-PUBLIC 部分（Constitution は公開可、内部レビューメモは不可）

→ **Dev `CLAUDE.md` confidentiality boundary と完全整合**。違反した内容を
public に出すことは絶対禁止。迷ったら ecri に確認。

## 4. 参照ルール（5 環境拡張版）

| アクション | Papers の権限 |
|---|---|
| 自環境を読む | ✓ |
| 自環境に書く | ✓ |
| 他環境を読む | **✓ 全環境**（公開素材抽出のため） |
| 他環境に書く | **✗** |

Papers は公開発信のため全環境を読めるが、書き込みは自環境内のみ。

## 5. このリポが持つもの

```
sens-papers/
├── README.md
├── LICENSE-CC-BY-4.0       # papers/essays/technical の prose
├── LICENSE-MIT             # scripts/ のコード
├── CLAUDE.md               # 本文書
├── docs/OPERATING.md       # 公開運用規律
├── docs/glossary.md        # 公開用語予約 (Stories と定義同期/ステータス独立、2026-05-29 〜)
├── handover/               # Antifragile ハンドオーバー等
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

drafts/ ファイル名先頭 `_` は「非公開作業物」の印。`.gitignore` で
`drafts/_*` を ignore 済み（2026-05-20 RESOLVED）。

## 6. Lifecycle

```
他環境（Manifesto / Stories / Dev / Foundation）からの WIP 受領
    ↓
drafts/_<topic>.md として保存（unreviewed marker、_ prefix で gitignore）
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

## 7. Push / Commit Policy

- Private repo、**commit / push 許可**
- public site への公開判断は **ecri のみ**
- arXiv 投稿は **ecri 承認後のみ**
- drafts/_* は `.gitignore` 対象（誤公開防止の構造的ガード）

## 8. 判断基準（迷った時の優先順位）

1. **Confidentiality boundary 厳守**（OPERATING.md + Dev CLAUDE.md と整合）
2. **public-safe 検証**（ecri レビュー前に self-check）
3. **citation 可能性**（drafts/ は明示的に「not for citation」マーカー）
4. **Manifesto Constitution との整合**（公開エッセイが Constitution 条文と矛盾しないか）
5. **長期の正統性**（撤回より、最初から公開しない方が安全）

## 9. 緊急時の path 確認手順

何かが「変だ」と感じたら（編集が反映されない、ファイルが消えた、
remote が違う等）:

```bash
# 現在地確認
pwd && git rev-parse --show-toplevel

# remote 健全性
git fetch && git status -sb

# Dev からの dispatch 確認
ls /Users/ecri/.claude-worktrees/sens/sens/docs/governance/dispatch/sens-papers/ 2>/dev/null
ls /Users/ecri/.claude-worktrees/sens/sens/docs/archive/dispatch/sens-papers/ 2>/dev/null

# 過去 incident 確認
ls /Users/ecri/.claude-worktrees/sens/sens/docs/governance/decisions/ 2>/dev/null
```

異常を検知したら、本 repo `handover/` に状況メモを作成して ecri に報告する。

## 10. やらないこと（他環境への委譲）

| 対象 | 担当環境 |
|---|---|
| Constitution / Manifesto / Anchor の起草 | Manifesto |
| Application Story / Interview の起草 | Sens Stories |
| 技術仕様の起草 | Dev |
| License / SCA の起草 | Foundation |
| 内部情報の公開判断（最終承認） | ecri |

Papers は **公開可能な抜粋・引用・推敲・publishable deep-dive の起草** までを担う。
