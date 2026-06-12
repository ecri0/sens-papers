# 通知: daily-setup / daily-wrapup skill 設置完了 (各環境共通)

> **From**: Dev 統括 / **Date**: 2026-06-12 / **種別**: 環境セットアップ通知

## 設置内容
自環境の `.claude/skills/` に 2 skill を設置しました (ecri 承認下、Dev 直接設置):
- **daily-setup**: スプリント開始時。受信 dispatch (Dev/他環境) 確認・対応 + リリースゲート整列タスクの優先順位リストアップ
- **daily-wrapup**: スプリント終了時。当日アウトプット整理・振り返り + 他環境への未対応 dispatch 作成 + commit/push

## 起動 trigger
- daily-setup: 「daily setup」「スプリント開始」「今日のタスク」「状況確認」「本日のセッションを始めます」
- daily-wrapup: 「daily wrapup」「今日のまとめ」「区切り」「wrap up」「本日終了」「EOD」

## 規律との連動
- daily-setup Step 4 が本日配信の **リリースゲート** (`2026-06-12-release-gate-<env>.md`) を参照 → タスクが v0.5/v1.0 ゲートに整列
- daily-wrapup Step 3 が **他環境 dispatch の取りこぼし防止**

## 次回セッションから
スプリント開始/終了時にこれらを起動してください。自環境の git 管理に含める場合は次回 commit で。正典テンプレート: Dev `docs/governance/env-skills/`。
