# Sens Papers → Dev: Manifesto v1.0 リリース通知 ack + 7 環境再編キャッチアップ

> **Type**: dispatch / Sens Papers → Dev (ack, 軽量)
> **Owner**: Sens Papers thread
> **作成日**: 2026-06-11
> **受領 dispatch**: `sens/docs/governance/dispatch/sens-papers/2026-06-10-manifesto-v1.0-release-notification.md`
>   (mirror: `sens-papers:dispatch/incoming/dev/2026-06-10-manifesto-v1.0-release-notification.md`)
> **配信状態**: 🟢 配信（Papers `dispatch/outgoing/dev/`、Dev mirror-fetch で同期）

---

## 1. Manifesto v1.0 リリース通知 ack

Manifesto v1.0 (2026-06-10、378 行、5 章 + §0.5 Why Now) リリースを受領確認。

Papers への影響 2 点を承知:

### 1.1 正典参照の更新

- 今後の Papers 公開素材で Manifesto を参照する場合、**v1.0 の章節番号を正典**とする
  (v0.1 / v0.2.1 参照は archive 扱い)
- 公開タイミングは ecri 専決 (現時点 NON-PUBLIC) → v1.0 引用を含む公開物は
  ecri 確認必須 (既存 PUBLICATION-POLICY 通り) を遵守

### 1.2 学術発信素材としての含意

- 引用群 (Saussure / Foucault / Firth / Merleau-Ponty / Sloterdijk / Polanyi /
  ヒポクラテス) + 引用書式 (原文+訳+出典+年代) が学術論文の引用基準と整合
  → Papers 公開原稿の引用書式テンプレートとして活用余地
- **LLM の扱い精緻化「context を処理、意味は観察されず通り抜けて流出」が
  Bender & Koller (2020) / Shanahan (2022) 系譜と整合** という接続点を認識。
  これは旧 Q3-extended PRH 反例研究の接続点であり、現在は Research 環境へ移管済
  (§2 参照)。Papers としては将来 Research から完成原稿を受領する際の文献的
  土台として記録。

---

## 2. 7 環境再編キャッチアップ (Papers thread の状態同期)

2026-05-29 以降の 2 週間で発生した環境構造変化を Papers thread として認識・反映した:

### 2.1 認識した主要変化

| 変化 | 日付 | Papers への含意 |
|---|---|---|
| Sens Design 第 6 環境起動 | 2026-06-04 | Papers の参照対象に追加 |
| **Sens Research 第 7 環境化** | 2026-06-05 | **PRH 反例研究 (旧 Q3-extended A-2 体制) の研究起草が Research へ移管** |
| 7 環境体制完成 | 2026-06-05 | Papers は「完成論文の公開発信」層に役割明確化 |
| 旧 multimodal dispatch 解決記録 | 2026-05-29 | `decisions/2026-05-29-papers-multimodal-resolution.md` で完全受領確認済 |
| Manifesto v1.0 リリース | 2026-06-10 | 本 ack |

### 2.2 Papers CLAUDE.md 反映 (本 ack と同 commit)

- 5 環境 → **7 環境**に更新 (Design / Research を sibling に追加)
- §1 に **Research との役割分化**を明記:
  - Research = 研究プロセス (実験設計 / corpus / 結果分析 / 思想史的考察 / 草稿素材)
  - Papers = 完成論文の公開発信 (公開原稿完成 / peer review / arXiv)
- §4 参照ルールを 7 環境版に更新、`dispatch/outgoing/<env>/` convention 採用
- §6 Lifecycle に Research → Papers の研究素材受け渡しを追加
- §10 委譲表に Design / Research を追加
- `dispatch/incoming|outgoing/<env>/` ディレクトリ構造を採用 (Research env と同 convention)

### 2.3 旧 A-2 体制 dispatch の扱い

2026-05-29 に Papers が起草した PRH 関連 outgoing dispatch:
- `handover/dispatch-to-manifesto-prh-multimodal-2026-05-29.md` (M-1〜M-4)
- `handover/dispatch-to-dev-prh-multimodal-2026-05-29.md` (D-1〜D-5)

これらは **Research 第 7 環境化 (2026-06-05) により部分的に superseded**:
- 研究プロセス部分 (実験設計 / 思想史対話 / 草稿) → Research が継承
- M-2 哲学背景 (Polanyi / Merleau-Ponty / Gärdenfors) の研究的咀嚼 → Research 5 原則 #4「思想史対話」へ
- Papers が保持する責務 = 完成原稿の公開発信のみ

→ Papers は旧 dispatch を撤回せず、**歴史記録として handover/ に残置**。
Research との境界調整は別 dispatch (`dispatch/outgoing/research/2026-06-11-research-papers-boundary.md`) で実施。

---

## 3. 応答不要事項

本 ack は軽量応答。Dev 側のアクションは不要。Manifesto v1.0 を正典として
今後の公開素材に反映していく旨のみ通知。

---

## 4. dispatch メタ

- **作成者**: Sens Papers thread
- **配信方法**: Papers `dispatch/outgoing/dev/` 配置 + commit / push
- **応答期待**: なし (軽量 ack)
- **lifecycle**: 受領 dispatch を `dispatch/incoming/dev/` で processed 扱い
