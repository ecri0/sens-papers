# Papers → Dev: v0.5 preprint 第1本 主題確定 (ADR-043 観測中立性) + public-safe 素材要求

> **Type**: dispatch / Sens Papers → Dev (主題確定記録 + 素材要求)
> **Owner**: Sens Papers thread
> **作成日**: 2026-06-12
> **配信状態**: 🟢 配信 (Papers `dispatch/outgoing/dev/`)
> **起源**: `2026-06-12-release-gate-papers.md` §2「v0.5 preprint 第1本の主題は ecri 確定待ち」
> **緊急度**: 🟡 中 (v0.5 ゲート blocking 解除)

---

## 1. 主題確定

ecri 確定 (2026-06-12): **v0.5 preprint 第1本の主題 = ADR-043「観測中立性
(Observational Neutrality)」**。

候補 3 件 (ADR-043 観測中立性 / Q3-extended PRH / IQ-MS1) から ADR-043 を選択。

### 選定の含意
- **起草分担**: ADR-043 は Dev 内部 ADR (草稿 #44 進行中)。preprint は **public-safe
  な概念・哲学レベル**で Papers が起草。内部 ADR 実装詳細は **含めない**。
- **EW-001 essay との関係**: EW-001「意味のレントゲン」(essay、署名済・公開保留) は
  意味記述レイヤーの導入。本 preprint (観測中立性) は **研究原則の学術定式化**で、
  読者層 (Inner Circle 学術) と粒度が異なり重複しない。
- **Sphere 哲学との連動**: 観測中立性 = Research 5 原則 #1、Sphere 哲学 §3(j) と整合。
  Manifesto v1.0 (公開予定) の Sphere 概念と正典整合させる。

---

## 2. Dev への public-safe 素材要求

preprint 起草のため、以下の **public-safe な素材**を Dev (および該当時 Research)
から供給いただきたい。**内部 ADR 本文・実装詳細・内部メトリクスは不要** (機密境界)。

| # | 要求素材 | public-safe レベル | 用途 |
|---|---|---|---|
| MR-1 | ADR-043 観測中立性の **概念定義** (何を「観測中立」とするか) | 概念・定義のみ (実装/閾値なし) | preprint §定義節 |
| MR-2 | 観測中立性が **規範化を避ける**という主張の論拠 | 哲学的論拠 (Sphere §3(j) 公開部分) | preprint §論証節 |
| MR-3 | 観測中立性の **公刊文献的系譜** (測定理論 / 観測者効果 / 価値中立性論等) | 公刊文献のみ | preprint §関連研究 |
| MR-4 | 観測中立性と **既存 SAE/interpretability 研究**の関係 (公開可能範囲) | 一般的公刊系譜のみ | preprint §技術的背景 |

→ 供給は Dev `dispatch/outgoing/papers/` ないし ecri 仲介。Research 5 原則 #1
関連は Research 環境からの供給も可 (思想史対話ノートと連携)。

## 3. 機密境界 self-guard (Papers 側の約束)

本 preprint に **含めないもの** (release-gate §3 + CLAUDE.md §3):
- ADR-043 内部本文 / ADR revert 履歴 / Polaris 戦略 / GPU 予算 / 内部 KPI /
  Fragile Triad / ビジネスマージン / Apple Silicon specifics / 未公開実験詳細
- 公開は ecri 専決 + Foundation 弁護士機密確認を経る

## 4. Papers 側の即時着手 (素材待ちと並行)

- drafts/ に preprint scaffold を起草 (gitignore 済 WIP)。構成 + 機密境界 +
  素材スロット (MR-1〜4 の挿入位置) を先行整備
- 公刊文献の予備スキャン (観測者効果 / 価値自由 Wertfreiheit / 測定の理論負荷性等)

## 5. dispatch メタ
- 応答期待: Dev → MR-1〜4 の public-safe 素材供給 (`dispatch/outgoing/papers/` or ecri 仲介)
- 連動: v0.5 ゲート preprint 1本 (2-3本枠)。EW-001 essay と合わせ v0.5 充足に前進
