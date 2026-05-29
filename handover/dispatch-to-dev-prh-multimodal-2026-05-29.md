# Sens Papers thread → Dev 統括: PRH 反例 × 多モダリティ実装含意レビュー依頼 (初動)

> **Type**: dispatch / Sens Papers → Dev (via ecri)
> **Owner**: Sens Papers thread
> **作成日**: 2026-05-29
> **配信状態**: 🟢 配信（Papers `handover/` 配下、Dev mirror-fetch で同期）
> **配信先 thread**: Sens Dev 統括スレッド (`/Users/ecri/.claude-worktrees/sens/sens/`)
> **緊急度**: 🟡 中（A-2 体制始動の初動、Phase 4+ 実装連動の先取り）
> **承認根拠**: ecri 承認 2026-05-29
>   - Q3-extended (a)=A-2 / (b)=B-2 / (c)=C-1
>   - Q3-ext-(d) 「Papers が初動 dispatch を起草してよい」
> **応答先**: Dev → `sens/docs/governance/dispatch/sens-papers/` 経由で応答

---

## 1. Subject

PRH (Platonic Representation Hypothesis) 2025 反例研究と多モダリティ非依存
Feature 仮説の連動可能性 (Papers thread 評価: B-2 「連動あり」、C-1 「Phase 4+
で reserved deep-dive paper」) について、**Dev 環境の SAE 実装レベルでの
含意と経験的検証可能性**をレビュー依頼。

A-2 体制 (Papers 主導 + Manifesto/Dev 連動) における **Dev 環境の役割範囲**
を明確化することが本 dispatch の中心目的。

---

## 2. 経緯 (Papers thread での承認済事項)

- ecri 承認 2026-05-29: Q3-extended (a)(b)(c) Papers 推奨採用
  - (a) A-2 Papers 主導 + Manifesto/Dev 連動
  - (b) B-2 連動可能性あり
  - (c) C-1 reserved (Phase 4+ で着手余地確保、placeholder なし)
- Q3-ext-(d) 承認: Papers が初動 dispatch を起草、ecri 仲介で配信
- Papers glossary §2 予約済: モダリティ固有 SAE / モダリティ非依存 Feature
  / 共有埋め込み空間 (`sens-papers:docs/glossary.md`)
- MM-P3 即時承認: Confidentiality 拡張 3 項目を CLAUDE.md §3 + OPERATING.md
  に追加済（本 dispatch と同 commit）
  - 画像 SAE 訓練データの IP
  - 音声 SAE 訓練データの IP
  - 共有埋め込み空間の研究内部資料

---

## 3. Dev 統括への 5 依頼事項

### 依頼 D-1: PRH 2025 反例の経験的検証可能性レビュー 🟡

Papers `drafts/_research-and-direction.md` §C-6 で進行中の PRH 2025 反例
研究について、**Dev 側 SAE 実装で経験的検証可能か** をレビュー依頼。

確認したい点:
- 現行 `EleutherAI/sae-llama-3-8b-32x-v2` (131k features, Top-K=32) で PRH 反例
  に該当する条件を経験的に再現可能か
- 「条件次第で収束する/しないが分岐する」という反例構造を SAE feature レベルで
  観測する手段（feature alignment 計測、cross-model 検証等）は実装上現実的か
- Fragile Triad 制約 (numpy<2, transformers<4.40, torch==2.2) 下で実行可能か

→ 検証可能であれば、Phase 4+ で Papers technical/ 配下 paper の経験的裏付け
として利用可能。検証困難であれば、Papers 側は理論レベル paper にスコープ縮小。

### 依頼 D-2: モダリティ固有 SAE 実装上の含意 🟡

Papers glossary §2「モダリティ固有 SAE」予約 (reserved Phase 4+) について、
Dev 側の実装ロードマップ上の位置づけを共有してほしい:

- 現行テキスト SAE (sparsify ライブラリ) を音声 / 画像に拡張する場合の
  アーキテクチャ含意
- モダリティ固有 SAE と共有埋め込み空間の実装関係（独立学習 → 後段アライメント
  vs 共同学習）
- Phase 4+ の見立てで、どのモダリティから先行着手見込みか

→ 公開情報の範囲のみで構わない。**内部ロードマップ詳細は不要**（Confidentiality
boundary 厳守、§5 参照）。Papers technical/ 配下 deep-dive paper の起草前提
として、公開可能なアーキテクチャ概念図レベルの情報があれば充分。

### 依頼 D-3: モダリティ非依存 Feature 仮説の実装検証フレーム 🟡

PRH 反例研究のフレーム (条件分岐構造) を **多モダリティ非依存 Feature 仮説の
経験的検証フレーム candidate** として転用する場合 (Papers Q3-ext (b) §3.2)、
Dev 側の実装上の含意:

- 異モダリティ SAE 間の feature alignment 計測手法 (現在の文献で確立されているか)
- Gärdenfors Conceptual Spaces の幾何的意味空間を SAE feature 空間にマッピング
  できる現実性
- Phase 4 SAE データ蓄積の見立て（経験的検証可能になるタイミング）

→ Phase 4+ paper の起草着手 trigger 判定材料。**「公開可能なレベルでの方法論
方向性」**まで Papers 側で把握したい。

### 依頼 D-4: Confidentiality 拡張 3 項目との照合 🟢

本 dispatch と同 commit で Papers CLAUDE.md §3 + OPERATING.md に追加した
3 項目:
- 画像 SAE 訓練データの IP
- 音声 SAE 訓練データの IP
- 共有埋め込み空間の研究内部資料 (Z アプローチ研究の内部進展)

これらが **Dev 環境の Confidentiality boundary と完全整合しているか** 確認:
- Dev `CLAUDE.md` の「Unpublished experiment specifics or internal metrics」
  との一致
- 訓練データ IP の取り扱いポリシーが Dev 内部で別途定められているか
- 「Z アプローチ」の用語が Dev 内部で確立済か / Papers 独自の概念整理か

→ 不整合があれば Papers 側で修正、Dev 内部で定義があれば Papers 側で参照
リンク追加。

### 依頼 D-5: Papers technical/ 配下 deep-dive paper の起草 trigger 設計 🟡

Q3-extended (c) C-1 採用前提:
- 起草着手の前提条件 3 件:
  - (i) Manifesto v0.X 射程拡張一節の完了
  - (ii) Foundation License v1.0 一般化の完了
  - (iii) Dev 側 PRH 反例の経験的検証データ蓄積 (Phase 4 SAE 実装後)

Dev 側の (iii) について、進行状況を共有する **trigger メカニズム** を設計したい:

| 案 | 内容 | Papers 予備見解 |
|---|---|---|
| 案 X-1 | Dev が四半期 wrap-up で Papers `handover/` 配下に状況更新 dispatch | ecri 負荷小、定期性あり |
| 案 X-2 | Papers が Mission Control mirror-fetch で四半期チェック、必要に応じて Dev に問い合わせ dispatch | Papers 主導、pull 方式 |
| 案 X-3 | (iii) 進捗が一定閾値 (例: feature alignment 計測の論文化見込み) に達した時点で Dev から Papers へ push | event-driven、見落としリスクあり |

→ Q3-ext-(c) で ecri 判断仰ぎ中の「起草着手 trigger 判定主体」と直結。Dev 視点
での実装可能性を踏まえた選好を共有してほしい。

---

## 4. Dev から Papers への期待応答

| 項目 | 必要応答 | 着手 unblock 対象 |
|---|---|---|
| D-1 PRH 反例経験的検証可能性 | 可 / 不可 / 条件付き | Papers technical/ paper のスコープ確定 (理論 only / 経験裏付け付) |
| D-2 モダリティ固有 SAE 公開可能アーキテクチャ概念 | 公開可情報の共有 | Papers technical/ deep-dive 起草の素材 |
| D-3 多モダリティ Feature 検証フレーム | 方法論方向性の公開可情報 | Phase 4+ 起草 trigger 判定材料 |
| D-4 Confidentiality 整合 | OK / 修正必要 / 内部定義リンク | Papers `docs/OPERATING.md` 整合確認完了 |
| D-5 trigger メカニズム選好 | 案 X-1 / X-2 / X-3 / その他 | ecri Q3-ext-(c) 判断材料 |

応答は **Dev → `sens/docs/governance/dispatch/sens-papers/`** に新規 dispatch
として配置。Papers が mirror-fetch で受領。

---

## 5. 期待しないこと

- 内部ロードマップ詳細の共有（Confidentiality boundary 厳守、公開可情報のみ）
- Dev 内部の Polaris 戦略 / GPU 予算 / 単価関連の言及
- Fragile Triad 制約の内部具体（公開済の制約名のみ参照可）
- 多モダリティ実装の網羅的レビュー（Phase 4+ で順次対応）
- Apple Silicon specifics（Dev `CLAUDE.md` 禁止項目）

→ **本 dispatch および応答 dispatch は両方とも Confidentiality boundary 内**
での情報交換に限る。

---

## 6. 既存案件との関係

- 2026-05-28 Phase 0 dispatch (`sens-papers:handover/dispatch-to-dev-2026-05-28.md`)
  §3 R1-R4 Dev 側残務との重複なし
- 2026-05-29 多モダリティ response (`sens-papers:handover/dispatch-to-dev-2026-05-29-multimodal-response.md`)
  §3 で予告した「Q3-ext-(d) 承認時に Manifesto/Dev 向け初動 dispatch を Papers
  起草」を本 dispatch で履行
- 並行 dispatch (`sens-papers:handover/dispatch-to-manifesto-prh-multimodal-2026-05-29.md`)
  と対をなす Dev 版

---

## 7. 関連参照

- 起源 dispatch: `sens/docs/governance/dispatch/sens-papers/2026-05-29-multimodal-public-writing-scope.md`
- Papers Q3-extended 詳細: `sens-papers:handover/dispatch-to-dev-2026-05-29-q3-extended-detail.md`
- Papers multimodal response: `sens-papers:handover/dispatch-to-dev-2026-05-29-multimodal-response.md`
- Papers glossary: `sens-papers:docs/glossary.md`
- Papers Confidentiality 拡張 (本 dispatch と同 commit): `sens-papers:CLAUDE.md` §3 / `sens-papers:docs/OPERATING.md`
- 並行 Manifesto 向け dispatch: `sens-papers:handover/dispatch-to-manifesto-prh-multimodal-2026-05-29.md`

---

## 8. dispatch メタ

- **作成者**: Sens Papers thread
- **配信方法**: Papers repo `handover/` 配下 + commit / push (Dev mirror-fetch で
  同期、Dev 側で直接読取可)
- **応答期待**: Dev → `sens/docs/governance/dispatch/sens-papers/` に新規
  dispatch 配置
- **archive trigger**: D-1〜D-5 応答受領 + Dev 側
  `governance/decisions/YYYY-MM-DD-papers-dev-prh-multimodal-resolution.md`
  記録完了 (Manifesto 側 dispatch と統合 decision も可)
