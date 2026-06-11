# Sens Papers → Dev: ecri 判断確定記録（Q1 / Q2 / Q4 / Q-RB、2026-06-11）

> **Type**: dispatch / Sens Papers → Dev（Mission Control 可視化用、状態記録）
> **Owner**: Sens Papers thread
> **作成日**: 2026-06-11
> **配信状態**: 🟢 配信（Papers `dispatch/outgoing/dev/`、Dev mirror-fetch で同期）
> **目的**: 2026-06-11 セッションで ecri が確定した Papers 保留 4 件を Dev 週次レポート / 統括が把握できるよう記録

---

## 1. 確定サマリ

| # | 事項 | ecri 判断（2026-06-11） |
|---|---|---|
| **Q1** | EW-001「意味のレントゲン」差し替え公開 | **署名する（内容承認）が公開は保留** |
| **Q2** | `_manifesto-core.md` write-and-hold 期間 | **v1.0 整合を取り続け保持**（M-3 案γ 異なる粒度で併存） |
| **Q4** | Papers thread 起動頻度 | **週次起動**（Mission Control 月曜同期） |
| **Q-RB** | Research↔Papers 境界 | **案α 承認**（§C のみ Research 移管 + Papers ポインタ化） |

---

## 2. Q1 — EW-001 署名済・公開保留

- **状態**: 差し替え候補 `drafts/_essay-reconciliation.md` は ecri **内容署名済**
  （2026-06-11）。機密 self-check CLEAN（pre-clear 済）。
- **公開トリガー**: **Manifesto v1.0 公開タイミングと足並み**。v1.0 が現在 ecri 専決
  NON-PUBLIC のため、v1.0 を参照する本 essay も公開保留。
- **Papers の行動**: essays/ ドロップインは **実行しない**（公開保留）。署名済・
  pre-clear 済の状態を維持し、v1.0 公開 GO 時に単一ドロップイン + push で即公開可能。
- **公開済 essays 現況**: 0 件（`ebd4029` publish → `6161a56` revert）。

## 3. Q2 — `_manifesto-core` 案γ 継続

- M-3 案γ（Manifesto v1.0 = フル思想 / Papers `_manifesto-core` = 公開可能語彙の
  予約簿、**異なる粒度で併存**）を ecri 確定。
- `_manifesto-core` は write-and-hold 継続、v1.0 と整合を取りながら保持。
- 公開 essay の語彙源として機能。Manifesto thread の M-3 正式応答があれば再整合。

## 4. Q4 — 週次起動

- Papers thread = **週次起動**。Mission Control 週次レポート（月曜）と同期。
- 緊急 dispatch / ecri 公開指示時はイベント駆動で随時起動可。
- CLAUDE.md §7 に反映済。

## 5. Q-RB — Research 境界 案α 承認

- ecri が **案α**（`_research-and-direction.md` §C のみ Research へ論理コピー +
  Papers 側ポインタ化、物理分割回避）を承認。
- Research 向け dispatch（`dispatch/outgoing/research/2026-06-11-research-papers-boundary.md`）
  に承認追記済。
- **未完の依存**: §C は gitignore 済（git 外）のため、Papers ポインタ化は
  **Research が `papers-draft/q3-extended-prh/` へ継承完了後**に実施（内容喪失防止）。
  継承方式・タイミングは Research の Q-RB2 応答待ち。

---

## 6. 本日 Papers 実施内容（commit 一覧）

| commit | 内容 |
|---|---|
| `c2c98bd` | 7環境キャッチアップ（CLAUDE.md 5→7、Manifesto v1.0 ack、Research 境界 dispatch） |
| `92dfdf6` | T1-T3（EW-001 self-check、glossary v1.0 整合、dispatch index） |
| （本 commit） | ecri 判断 Q1/Q2/Q4/Q-RB 確定記録 + CLAUDE.md 週次起動 + Research dispatch 承認追記 |

---

## 7. Dev 側で把握してほしい点

- Papers 週次レポート欄: 「EW-001 = ecri 署名済・公開保留（trigger = v1.0 公開）」
  「起動頻度 = 週次確定」を反映いただきたい
- Research 境界 案α は ecri 承認済。Research thread が §C 継承を進める際、Dev は
  mirror 経由で進捗監視（`alignment/with-papers-output.md` v0.2 改訂見込み）

---

## 8. dispatch メタ

- **作成者**: Sens Papers thread
- **配信方法**: Papers `dispatch/outgoing/dev/` + commit / push
- **応答期待**: なし（状態記録）。Dev 週次レポートへの反映のみ依頼
