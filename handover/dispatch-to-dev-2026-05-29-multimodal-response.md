# Sens Papers thread → Dev / ecri: 多モダリティ dispatch 受領 + Glossary 配置先判断 + Q3 統合

> **Type**: dispatch / Sens Papers → Dev / ecri
> **Owner**: Sens Papers thread
> **作成日**: 2026-05-29
> **配信状態**: 🟢 配信
> **受領 dispatch**: `sens/docs/governance/dispatch/sens-papers/2026-05-29-multimodal-public-writing-scope.md`（Dev 代行起草、2026-05-29）
> **応答先**: Dev 統括（記録）+ ecri（MM-P1 質問 + Q3-extended 質問）
> **緊急度**: 🟡 中（MM-P1 Glossary 配置先 = Phase 1 着手前 blocker）

---

## 1. 受領確認

2026-05-29 起草の多モダリティ public 発信 dispatch を Papers thread で受領した。

- 起源: なし（Dev 代行新規起草）+ `docs/handovers/sens-multimodal-handover/` 全 4 文書を Papers 視点で再構成
- 位置づけ: 5 環境拡張独自価値、原ハンドオーバー (旧 4 環境前提) には Papers 分なし
- 4 依頼事項: ①Glossary 配置先、②drafts/ メモ追加、③Confidentiality 拡張、④PRH 反例 × 多モダリティ連動
- ecri 判断仰ぎ事項: MM-P1〜MM-P4

ユーザー (ecri) 指示:
> 「Glossary 配置先（OPERATING.md / 独立 / Stories 参照）を Papers thread が判断、ecri に投げてください。PRH 反例 + 多モダリティ連動可能性は Papers Q3 と合流可です。」

→ 本 dispatch でこの 2 点に応答する。

---

## 2. MM-P1: Glossary 配置先 — Papers thread 判断

### 2.1 三選択肢の評価

| 配置案 | 利点 | 欠点 |
|---|---|---|
| **① OPERATING.md にセクション追加** | 既存ファイル、運用規律と用語が一箇所 | OPERATING.md は contributor 向け規律文書 = **単一責任違反**、Phase 4+ 用語拡張で肥大化、citation 単位が不明確 |
| **② 新規 `docs/glossary.md`** | 独立 citation 可、Stories とパラレル構造、Phase 4+ 拡張に対応、Papers 固有用語 (Public Multimodal Scope 🆕) の正当な居場所、public 出版物から URL 参照点として安定 | 新規ファイル、メンテ対象増加 |
| **③ Stories の Glossary 参照** | DRY、cross-env read で対応 | **Stories は internal Application Story 環境**、その glossary は人物 archetype 等のドメイン特化で Papers と mismatch、何より **public 文書から internal env を citation で pointing するのは confidentiality boundary 観点でリスク** (public arXiv paper の参照リンクが internal repo を指す構造は事故源)、Papers 固有 1 件 (Public Multimodal Scope) も収まらない |

### 2.2 Papers thread 推奨判断: **配置 ② 新規 `docs/glossary.md`**

#### 根拠

1. **Confidentiality boundary 適合**
   public 出版物 (essays/ / papers/ / technical/) からの citation 先が internal env (Stories) を指す構造は CLAUDE.md §3 + OPERATING.md の Confidentiality 原則と整合しない。Papers 内に閉じた glossary であれば、arXiv 等の外部発信時にも URL/anchor で安定参照可。

2. **単一責任原則**
   OPERATING.md = 「contributor 行動規律」、glossary = 「用語予約と定義」は別文書として分離するのが文書設計上クリーン。OPERATING.md は短く保ち、glossary は独立して成長させる。

3. **Stories とのパラレル構造**
   Stories thread も並行 dispatch で `meta/glossary.md` を持つ。Papers も同等の独立 glossary を持つことで、各環境が自前の用語管理をしつつ、ecri 仲介で同期する 5 環境拡張の自然な姿になる。

4. **Papers 固有用語の居場所**
   dispatch §3 依頼 1 で予約候補 10 件のうち 1 件 (Public Multimodal Scope 🆕) は **Papers 固有**と明示されている。配置 ③ (Stories 参照) では構造的に収まらない。

5. **citation 可能性**
   Papers 文書の判断基準 §8 #3「citation 可能性」と整合。drafts/ は「not for citation」だが、`docs/glossary.md` を canonical 化することで essays/ 公開時の用語安定性が確保される。

6. **拡張性**
   Phase 4+ で多モダリティ paper / technical が増えるとき、独立 glossary は status 表 (active / reserved / research-watch) を持って自然に成長できる。OPERATING.md 内では肥大化制御が難しい。

### 2.3 sub-question: Stories glossary との同期方式

配置 ② を採用する場合の派生論点として、Stories glossary と Papers glossary の同期方式を ecri 確認したい。**Papers thread は他環境への書き込み権限を持たない**ため、同期は ecri 仲介前提。

| 同期方式 | 利点 | 欠点 |
|---|---|---|
| **A. 各環境独立 (同期しない)** | 各環境のドメイン特化を尊重、運用シンプル | 同一用語の定義が乖離する事故リスク |
| **B. Stories canonical、Papers が public-safe 抽出** | 起源を Stories に統一 | Stories は internal、Papers public 用と方向性が異なる |
| **C. ecri 経由で双方同期 (定義同期、ステータス独立)** (Papers 推奨) | 定義は共有、ステータス (active/reserved/research-watch) は各環境の発信フェーズに応じて独立 | ecri 負荷 |

→ 推奨は **C** だが ecri 判断仰ぎ。

### 2.4 ecri への質問 (MM-P1)

> **Q MM-P1**: Papers Glossary 配置先について、Papers thread の判断として **配置 ② 新規 `docs/glossary.md` 起草** を推奨します (根拠は本 dispatch §2.2)。
>
> - 承認いただける場合、起草着手します (依頼 1 完了)
> - 修正案 (例: 配置 ① + OPERATING.md 整理) があればご指示ください
>
> **Q MM-P1-sub**: 配置 ② 採用時、Stories glossary との同期方式は本 dispatch §2.3 の **C (ecri 経由で定義同期 / ステータス独立)** を推奨しますが、ご判断願います。

---

## 3. Papers Q3 統合: PRH 反例研究化 × 多モダリティ認識論連動

ユーザー指示「PRH 反例 + 多モダリティ連動可能性は Papers Q3 と合流可」を受け、2026-05-28 dispatch §2 で投げた **Q3** と本多モダリティ dispatch の **MM-P4 / 依頼 4** を統合し、**Q3-extended** として ecri に投げ直す。

### 3.1 統合前の Q3 (2026-05-28)

> **Q3**: PRH 2025 反例の研究テーマ化 (`_research-and-direction.md` §C-6) の進行体制 — Papers 内部研究ノートにとどめるか、Manifesto / Dev と連動するか

### 3.2 統合前の MM-P4 (2026-05-29)

> **MM-P4**: PRH 反例 + 多モダリティ連動の研究化体制 (Papers 内部 / Manifesto+Dev 連動) — 緊急度中、Papers Q3 と合流

Dev 提案 (本 dispatch §3 依頼 4):
> 連動する場合、Papers の `technical/` 配下に将来「多モダリティと PRH 反例の交点」という deep-dive paper の予約余地を確保

### 3.3 Q3-extended (統合形)

> **Q3-extended**: `_research-and-direction.md` §C-6 で進行中の **PRH 2025 反例研究** の進行体制について、以下を一括判断いただきたい:
>
> - **(a)** 研究化体制: Papers 内部研究ノートにとどめるか、Manifesto / Dev と連動するか
> - **(b)** 多モダリティ認識論 (Polanyi 暗黙知 / Merleau-Ponty 身体現象学 / Gärdenfors Conceptual Spaces) との **連動可能性**: あり / なし / 要追加調査
> - **(c)** 連動「あり」の場合、Papers `technical/` 配下に **「多モダリティと PRH 反例の交点」** の deep-dive paper を予約するか (Dev 提案):
>     - reserved (Phase 4+ で着手余地確保のみ)
>     - research-watch (背景研究を継続、起草未定)
>     - 未定 (本判断見送り)
>
> Papers thread からの予備見解: **PRH = 同一意味の異モデル間収束** という主張は本質的に **モダリティ非依存 Feature 仮説** と概念構造が近接 (両者とも「表現基底の差異を越えた意味の不変性」を扱う)。2025 反例も「特定条件下では収束しない」という形で多モダリティ条件分岐と並列構造を持つ。→ **連動可能性 (b) はあり** と評価し、**(c) reserved** を推奨。ただし起草着手は Q3-(a) 体制判断後。

---

## 4. 残依頼の handling 方針

| 依頼 | Papers thread 方針 | 着手条件 |
|---|---|---|
| 依頼 1: Glossary 配置先 | §2 で判断、ecri MM-P1 承認待ち | MM-P1 承認 → 起草着手 |
| 依頼 2: drafts/ 4 件 多モダリティ視点メモ追加 | Phase 1 着手の一部として実施予定 | ecri Q1 (EW-001 タイミング) 判断と並行可、Q2 (write-and-hold 期間) の判断は不要 (メモ追加は write-and-hold 中も可) |
| 依頼 3: Confidentiality 拡張 (画像/音声 SAE 訓練データ IP 等) | MM-P3「即時 / Q1 公開承認後」のうち **即時実施を推奨** (公開前に boundary 拡張するのが安全方向) | ecri MM-P3 判断後 |
| 依頼 4: PRH 反例 × 多モダリティ連動 | §3 で Q3 統合、ecri Q3-extended 判断待ち | Q3-extended (a)(b)(c) 判断後 |

依頼 2 のメモ追加は **`_review-packet.md` を除く 3 件** に対し、Dev 提示の視点でヘッダコメント追記 (本文書き換えなし) の形を想定。`_manifesto-core.md` には多モダリティ語彙の予約追記、`_research-and-direction.md` には §C-6 への (b)(c) 議論追記、`_essay-reconciliation.md` には Manifesto 射程拡張一節との整合確認メモ。

---

## 5. ecri 判断仰ぎ事項 (再掲、本 dispatch 経由)

| # | 事項 | 起源 |
|---|---|---|
| **MM-P1** | Glossary 配置先 (Papers 推奨: 配置 ② `docs/glossary.md`) | 本 dispatch §2 |
| **MM-P1-sub** | Stories glossary との同期方式 (Papers 推奨: C 定義同期/ステータス独立) | 本 dispatch §2.3 |
| **Q3-extended** | PRH 反例研究 (a) 体制 / (b) 多モダリティ連動可能性 / (c) deep-dive paper 予約 | 本 dispatch §3、Q3 (2026-05-28) + MM-P4 統合 |
| MM-P2 | drafts/ メモ追加の優先度 | 多モダリティ dispatch §9 (Papers 方針: write-and-hold 中も実施可、低優先度) |
| MM-P3 | Confidentiality 拡張のタイミング | 多モダリティ dispatch §9 (Papers 推奨: 即時) |
| Q1 | EW-001 差し替え公開タイミング | 2026-05-28 dispatch |
| Q2 | `_manifesto-core` write-and-hold 期間 | 2026-05-28 dispatch |
| Q4 | Papers thread 起動頻度 | 2026-05-28 dispatch |

---

## 6. Dev 側応答記録の見立て

dispatch メタ §11 に従い、ecri 判断受領後の Dev 側記録:
- `sens/docs/governance/decisions/YYYY-MM-DD-papers-multimodal-resolution.md` 作成
- 本 dispatch (`sens-papers:handover/dispatch-to-dev-2026-05-29-multimodal-response.md`) を入力として参照リンク
- archive trigger: Papers thread が Glossary 起草 + drafts/ メモ + Confidentiality 拡張 + PRH 連動結論を全て完了 → Dev 記録 → 多モダリティ dispatch を `archive/dispatch/sens-papers/` 移動

---

## 7. dispatch メタ

- **作成者**: Sens Papers thread
- **配信方法**: Papers repo `handover/` 配下に配置 + commit / push (Dev mirror-fetch で同期)
- **応答期待**: ecri MM-P1 + MM-P1-sub + Q3-extended の判断 → Papers thread 起草着手
- **archive trigger**: 4 依頼すべて完了 + Dev 側 decision 記録
