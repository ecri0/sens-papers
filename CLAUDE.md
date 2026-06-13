# Sens Papers — Project Instructions for Claude

## 1. Project Identity
- Repo: ecri0/sens-papers (Private)
- Role: Sens プロジェクト **7 環境**のうち **Sens Papers 環境** —— public-facing
  essays / papers / technical writing の起草・推敲・**公開発信**
- 戦略層: Antifragile 戦略の 5 層構造のうち、全層の **公開発信を担う横断環境**
  （いずれの戦略層にも直接属さない）
- Canonical working directory: `/Users/ecri/.claude-worktrees/sens/sens-papers/`
  （Mission Control mirror 対象、sibling 統一 2026-05-28）
- Sibling environments（**7 環境体制、2026-06-05 完成**）:
  - `/Users/ecri/.claude-worktrees/sens/sens-manifesto/` — Manifesto (哲学/Constitution)
  - `/Users/ecri/.claude-worktrees/sens/sens-stories/` — Stories (物語/例)
  - `/Users/ecri/.claude-worktrees/sens/sens/` — Dev (技術実装/統括/ADR 採択)
  - `/Users/ecri/.claude-worktrees/sens/sens-foundation/` — Foundation (License/SCA/SSF)
  - `/Users/ecri/.claude-worktrees/sens/sens-design/` — Design (視覚/UI-UX/ブランド、第6環境 2026-06-04)
  - `/Users/ecri/.claude-worktrees/sens/sens-research/` — Research (研究プロセス/USID 探索/実証検証、第7環境 2026-06-05)
- **Research との役割分化（2026-06-05、重要）**:
  - Research = 研究プロセス（実験設計 / corpus 選定 / 結果分析 / 思想史的考察 / 草稿素材）
  - Papers = **完成論文の公開発信**（公開原稿完成 / peer review 提出 / arXiv）
  - PRH 反例研究（旧 Q3-extended A-2 体制）の研究起草は **Research へ移管**、Papers は受領後の公開発信
  - 受け渡し: Research `papers-draft/<topic>/` → ecri 仲介 → Papers
  - 境界定義: `sens-research:alignment/with-papers-output.md`

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

### 3.1 対外表現ルール（2026-06-13 Dev 確定、公開発信の framing 統制）

- **補完関係 framing**: 対外発信は「LLM と Sens は**補完関係**」「同一の根源を
  探る共同探究」。LLM 能力限界等の**対立的・優劣的表現を避ける**。Anthropic /
  Goodfire は補完路線 (Mechanistic Interpretability と共鳴)。
- **意味組成仮説の提示**: 「自己組織化を**観測する**科学的問い」として提示
  （断定せず、検証中の仮説）。
- **効率フレーミング除外 (基準4 / RT-K)**: 「LLM 効率構造変化」フレーミングを
  外す。公開可は純粋研究主張のみ（単義性 / 不変性 / 人間整合 / **融合カバレッジ**
  ＝「いかなる単一モデルも融合により超える」と scope 明記）。基準4 を無条件
  「USID は LLM を情報量で上回る」とは書かない（融合 scope 限定必須）。Polaris
  戦略・効率優位・業界構造変化の機密境界を越えない。
- 公開判断時は Dev / ecri レビュー（機密境界確認）。

## 4. 参照ルール（7 環境版）

| アクション | Papers の権限 |
|---|---|
| 自環境を読む | ✓ |
| 自環境に書く | ✓ |
| 他環境を読む | **✓ 全 6 環境**（Manifesto/Stories/Dev/Foundation/Design/Research、公開素材抽出のため） |
| 他環境に書く | **✗**（dispatch は `dispatch/outgoing/<env>/` 起草 → ecri 仲介） |

Papers は公開発信のため全環境を読めるが、書き込みは自環境内のみ。
他環境への要求・応答は `dispatch/outgoing/<env>/` に起草し ecri 仲介で配信。

## 5. このリポが持つもの

```
sens-papers/
├── README.md
├── LICENSE-CC-BY-4.0       # papers/essays/technical の prose
├── LICENSE-MIT             # scripts/ のコード
├── CLAUDE.md               # 本文書
├── docs/OPERATING.md       # 公開運用規律
├── docs/glossary.md        # 公開用語予約 (Stories と定義同期/ステータス独立、2026-05-29 〜)
├── handover/               # Antifragile ハンドオーバー + 過去 outgoing dispatch
├── dispatch/               # 環境間 dispatch（2026-06 convention）
│   ├── incoming/<env>/     # 他環境からの受信（ecri 仲介で配置）
│   └── outgoing/<env>/     # 他環境への送信（ecri 仲介で配信）
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
他環境（Manifesto / Stories / Dev / Foundation / Research）からの WIP / 研究素材受領
  ※ Research → Papers の研究素材は papers-draft/<topic>/ 経由（完成原稿化が Papers の責務）
    ↓
drafts/_<topic>.md として保存（unreviewed marker、_ prefix で gitignore）
    ↓
推敲（Papers thread）+ confidentiality check
    ↓
ecri レビュー
    ↓
essays/ / papers/ / technical/ へ promote（publish）
    ↓
site/ に反映、必要なら arXiv 投稿（peer review 提出は Papers 主担当）
    ↓
（withdraw 必要時）revert commit + index 更新（EW-001 経緯参照）
```

## 7. Push / Commit Policy

- Private repo、**commit / push 許可**
- public site への公開判断は **ecri のみ**
- arXiv 投稿は **ecri 承認後のみ**
- drafts/_* は `.gitignore` 対象（誤公開防止の構造的ガード）
- **起動頻度: 週次**（2026-06-11 ecri 確定、Q4）。Mission Control 週次レポート
  （月曜）と同期。緊急 dispatch / ecri 公開指示時はイベント駆動で随時起動可。

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
| 視覚 / UI-UX / ブランド | Design |
| 研究プロセス（実験設計 / corpus / 結果分析 / 思想史的考察 / 研究草稿素材） | **Research** |
| 内部情報の公開判断（最終承認） | ecri |

Papers は **公開可能な抜粋・引用・推敲・publishable deep-dive の起草、および
Research から受領した研究素材の完成原稿化・公開発信（peer review / arXiv）** を担う。
