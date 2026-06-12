---
name: daily-wrapup
description: スプリント終了時の整理・振り返り — 当日アウトプットを整理し、他環境への未対応 dispatch があれば作成、commit/push。「daily wrapup」「今日のまとめ」「区切り」「wrap up」「終了」等で起動。
---

# Daily Wrapup — スプリント終了 整理・振り返り (各環境共通)

7 環境 SDD の各環境がスプリント終了時に実行する。当日のアウトプットを整理し、**他環境への連絡が必要なのに未作成の dispatch を取りこぼさない**ことが要点。

## 起動 trigger
- 「daily wrapup」「今日のまとめ」「区切り」「wrap up」「本日終了」「EOD」
- `/daily-wrapup`

## 前提
- 自環境ルート = この repo。Dev repo = `/Users/ecri/.claude-worktrees/sens/sens/`
- 送信経路: 自環境の dispatch 規約 (CLAUDE.md 参照)
- push ポリシー: 各環境 CLAUDE.md に従う (private repo は push 可、Stories 等は「まとめて push」方針あり)

## 実行ステップ

### Step 1: 当日アウトプットの整理
```bash
git log --since="$(date +%Y-%m-%d) 00:00" --oneline
git status -sb
```
当日の commit + 未コミット変更を把握。未コミットがあれば内容を確認してまとめる。

### Step 2: 振り返り (リリースゲート進捗)
- 当日の成果が自環境の v0.5 / v1.0 ゲート (`dispatch/incoming/dev/2026-06-12-release-gate-<env>.md`) のどの項目を前進させたか
- 達成 / 残 / 次セッションへの申し送り

### Step 3: 他環境への dispatch 取りこぼし確認 ⭐
当日の作業で **他環境に伝えるべきこと**が発生していないか点検:
- Dev 統括に報告すべき進捗・完了・確認事項 → `dispatch/outgoing/dev/` (or 自環境規約)
- 他環境 (Manifesto↔Foundation 等) への連絡 → 自環境の `dispatch/<env>-to-<target>/`
- **未作成のものがあれば、ここで作成** (self-contained に、相手が単独で読めるよう)
- 直接書き込めない他環境へは「ecri 経由 or Dev cp 代行」の経路を明示 (operational-rules / charter §11.5)

### Step 4: 受領記録の完結
- 当日受領した dispatch の ack/receipt が未作成なら作成
- archive 可能 (trigger 完了) なものは自環境規約で archive

### Step 5: commit + push
```bash
git add -A
git commit -m "<当日サマリ>"
# push は CLAUDE.md ポリシーに従う (まとめて push 方針の環境は ecri レビュー後)
git push origin main   # 方針が push 可の場合
```

### Step 6: ecri へ EOD サマリ提示
- 当日の成果 (commit 数 + 主要アウトプット)
- リリースゲート進捗
- 作成した outgoing dispatch (配信が必要なもの = ecri 共有 or Dev cp 代行依頼)
- 次セッションへの申し送り

→ **未対応 dispatch がゼロ**であることを確認して終了。
