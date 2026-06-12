---
name: daily-setup
description: スプリント開始時のセットアップ — 自環境への dispatch (Dev/他環境) を確認・対応し、リリースゲートに整列したタスクを優先順位付きでリストアップ。「daily setup」「スプリント開始」「今日のタスク」「状況確認」等で起動。
---

# Daily Setup — スプリント開始セットアップ (各環境共通)

7 環境 SDD の各環境がスプリント開始時に実行する。Dev の `sens-mission-daily` (全環境横断) の各環境版。**自環境視点**で受信 dispatch を捌き、リリースゲートに整列したタスクを提示する。

## 起動 trigger
- 「daily setup」「スプリント開始」「今日のタスク」「状況確認」「本日のセッションを始めます」
- `/daily-setup`

## 前提 (各環境共通の場所)
- 自環境ルート = この repo (例: `sens-foundation/`)。Bash の cwd は自環境
- Dev repo (絶対パス) = `/Users/ecri/.claude-worktrees/sens/sens/`
- 受信経路: ① 自環境 `dispatch/incoming/dev/`(Dev からの ack/通知) ② Dev `docs/governance/dispatch/<自環境名>/`(Dev からの依頼)
- 送信経路: 自環境の dispatch 規約 (CLAUDE.md 参照。多くは `dispatch/outgoing/dev/`、Manifesto 等は `dispatch/<env>-to-<target>/`)

## 実行ステップ

### Step 1: 自環境の sanity check + 前回からの状態
```bash
pwd && git rev-parse --show-toplevel && git remote -v | head -1
git log --oneline -5
git status -sb
```
期待値と乖離があれば CLAUDE.md の緊急時手順へ。

### Step 2: 受信 dispatch の確認 (2 経路)
```bash
# ① Dev からの ack/通知 (自環境内)
ls -t dispatch/incoming/dev/ 2>/dev/null | head -10
# ② Dev からの依頼 (Dev repo 内、絶対パス)
ENV=$(basename "$(git rev-parse --show-toplevel)")
ls -t /Users/ecri/.claude-worktrees/sens/sens/docs/governance/dispatch/$ENV/ 2>/dev/null | head -10
```
未読・未対応のものを特定 (前回 wrap-up 以降の新規)。

### Step 3: 未対応 dispatch への対応
- 各 dispatch を読み、自環境の作業に落とす
- 受領確認が必要なものは、自環境 dispatch 規約で軽量 ack / 正式記録を作成 (新運用 2 階層: `*-ack.md` 1-3 行 / `*-receipt.md` 50-300 行)
- 他環境への波及が必要なら Step 5 で outgoing 作成

### Step 4: リリースゲートの参照 (タスク整列の基準)
```bash
ls dispatch/incoming/dev/2026-06-*release-gate-*.md 2>/dev/null
```
自環境の v0.5 / v1.0 ゲート (`2026-06-12-release-gate-<env>.md`) を確認。今日のタスクは**このゲートに整列**させる。

### Step 5: タスク優先順位リストアップ
以下を統合して、優先順位付きタスクリストを提示:
- 未対応 dispatch (Step 3)
- リリースゲート上の自環境責務 (Step 4)
- 自環境の進行中タスク (前回 wrap-up の残)

各タスクに **「どのリリースゲート (v0.5/v1.0) のためか」を明示**。ecri に確認が必要な点は 1 件ずつ選択式で提示 (ecri working-style: ポップアップ 1 件ずつ)。

### Step 6: ecri へ状況サマリ提示
- 受信 dispatch 件数 + 対応状況
- 本日の推奨タスク (優先順位 + ゲート整列)
- ecri 判断待ち事項

→ ecri 承認後、推奨順に着手。
