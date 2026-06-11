# Sens Papers — Dispatch Index

環境間 dispatch の index と convention 定義（2026-06 採用、Research env と同型）。

## Convention

| ディレクトリ | 用途 |
|---|---|
| `dispatch/incoming/<env>/` | 他環境からの受信（ecri 仲介で配置） |
| `dispatch/outgoing/<env>/` | 他環境への送信（ecri 仲介で配信、Papers は他環境へ直接 write 不可） |

`<env>` = dev / manifesto / stories / foundation / design / research

- ファイル名: `YYYY-MM-DD-<topic>.md`
- Papers は private repo へ commit / push 可。dispatch は内部文書（公開物ではない）。
- 公開物（essays / papers / technical）への dispatch 内容の転載は ecri ゲート必須。

## Incoming（受信）

| date | from | topic | 状態 |
|---|---|---|---|
| 2026-06-10 | dev | [Manifesto v1.0 リリース通知](incoming/dev/2026-06-10-manifesto-v1.0-release-notification.md) | ✅ processed（ack 済 → outgoing/dev/2026-06-11） |

## Outgoing（送信）

| date | to | topic | 状態 |
|---|---|---|---|
| 2026-06-11 | dev | [Manifesto v1.0 ack + 7環境キャッチアップ](outgoing/dev/2026-06-11-manifesto-v1.0-ack.md) | 🟢 配信（軽量、応答不要） |
| 2026-06-11 | research | [Research↔Papers 境界提案 (C-4 応答, Q-RB1〜4)](outgoing/research/2026-06-11-research-papers-boundary.md) | 🟢 ecri 案α承認、Research 継承タイミング応答待ち |
| 2026-06-11 | dev | [ecri 判断確定記録 Q1/Q2/Q4/Q-RB](outgoing/dev/2026-06-11-ecri-decisions-q1-q2-q4-qrb.md) | 🟢 配信（状態記録、応答不要） |

## 歴史 dispatch（`handover/` 残置、convention 採用前）

以下は 2026-05 の旧方式（`handover/` 直置き）。**Dev の決定記録が `handover/` パスを
参照しているため移送せず残置**（cross-env 参照の安定性優先）。論理的には
`outgoing/<env>/` 相当。

| date | logical dest | file |
|---|---|---|
| 2026-05-28 | outgoing/dev | [handover/dispatch-to-dev-2026-05-28.md](../handover/dispatch-to-dev-2026-05-28.md)（Phase 0 完了報告 + R1-R4） |
| 2026-05-29 | outgoing/dev | [handover/dispatch-to-dev-2026-05-29-multimodal-response.md](../handover/dispatch-to-dev-2026-05-29-multimodal-response.md) |
| 2026-05-29 | outgoing/dev | [handover/dispatch-to-dev-2026-05-29-q3-extended-detail.md](../handover/dispatch-to-dev-2026-05-29-q3-extended-detail.md) |
| 2026-05-29 | outgoing/dev | [handover/dispatch-to-dev-prh-multimodal-2026-05-29.md](../handover/dispatch-to-dev-prh-multimodal-2026-05-29.md)（Research 移管で部分 superseded） |
| 2026-05-29 | outgoing/manifesto | [handover/dispatch-to-manifesto-prh-multimodal-2026-05-29.md](../handover/dispatch-to-manifesto-prh-multimodal-2026-05-29.md)（Research 移管で部分 superseded） |

> `handover/handover-to-sens-papers.md` は dispatch ではなく Antifragile 環境
> ハンドオーバー本体 → `handover/` に維持。
