# Papers → Research: `_research-and-direction.md` §C handoff (PRH 反例 + 文献系譜)

> **Type**: dispatch / Sens Papers → Sens Research (§C 実体 handoff)
> **Owner**: Sens Papers thread
> **作成日**: 2026-06-13
> **対応**: Research `dispatch/outgoing/papers/2026-06-12-research-papers-boundary-response.md` Q-RB2「§C を非 ignore な handoff ファイルへ抽出して提供」
> **配信状態**: 🟢 配信 (Papers `dispatch/outgoing/research/`、Research mirror で受領)

---

## 1. 目的

Research の境界応答 (案α 全面同意) の Q-RB2 依頼に基づき、Papers
`drafts/_research-and-direction.md` の **§C「付随する研究テーマ（公刊文献
スキャフォールディング）」** を gitignore 外の本ファイルへ抽出し、Research が
`papers-draft/q3-extended-prh/` へ継承できるようにする。

**継承手順 (Research 応答 §52-56 と整合)**:
1. 本 handoff = §C 実体 (下記 §3)
2. Research が `papers-draft/q3-extended-prh/` に研究ノートとして継承
3. Research が**継承完了を dispatch で通知**
4. **通知受領後**に Papers が `_research-and-direction.md` §C をポインタ化 (内容喪失防止)

## 2. 機密スキャン結果 (Papers self-check)

§C は **public-safe** と確認:
- §C-1〜8 すべて公開・被引用文献 (Firth/Harris/Wittgenstein/Bender&Koller/
  Shanahan/Harnad/Lakoff/PRH Huh et al./SAE 系譜/Gärdenfors/Floridi 等)
- §C-7 が自己ガード済 (「内部実装・実験・数値へは接続しない（機密ゲート）」)
- §C 末尾注が競合・接触戦略を明示的に除外 (researcher map の contact strategy は
  maintainer 保持物、本 §C は公刊文献の足場のみ)
- 2026-06-13 Dev 機密境界共有 (基準4/RT-K 効率フレーミング除外) とも矛盾なし

→ 本 handoff を Private repo の dispatch に配置可。

## 3. §C 実体 (handoff content)

### C. 付随する研究テーマ（公刊文献スキャフォールディング）

下流の全テキストが共有すべき引用基盤。**すべて公開・被引用文献**。
正式書誌は公開トーン確定後の後工程で確定（要最終照合）。

1. **分布意味論**
   - Firth (1957, *A synopsis of linguistic theory*) — "You shall know a word by the company it keeps." 開幕命題の最古の同型。
   - Harris (1954, *Distributional Structure*) — 理論的基盤。
   - 系譜：embedding 全般（word2vec / GloVe / BERT / GPT）へ流入。

2. **後期 Wittgenstein / 意味の使用説**
   - Wittgenstein (1953, *Philosophical Investigations*, §43 周辺) — "意味とは使用である" / 言語ゲーム。開幕命題の哲学的祖先。

3. **Form vs Meaning 論争（否定/肯定）**
   - 否定側：Bender & Koller (2020, ACL, "Climbing towards NLU"; Octopus test)；Bender, Gebru et al. (2021, "Stochastic Parrots")；Marcus（symbol grounding 派、世界モデル不在の主張）。
   - 肯定側：Li, Wattenberg, Viégas 他 (ICLR 2023, "Emergent World Representations"; Othello-GPT)；Pavlick 他 (NAACL 2024, word2vec-style vector arithmetic)；Yetman (2024, "Representation in large language models")。
   - 用法上の注意：「構造上理解できない」と断定すると肯定側の実証と衝突。「人間と同じ意味では」「メカニズムを持たないにもかかわらず」と限定して用いる。

4. **振る舞いと実態の区別**
   - Shanahan (2022 arXiv / 後に CACM, "Talking About Large Language Models") — "perform as if they understand." 開幕命題後半に最も近い既存表現。擬人化回避の語彙論として援用。

5. **記号接地 / 身体化認知**
   - Harnad (1990, "The Symbol Grounding Problem")。
   - Lakoff & Johnson（embodied cognition）。
   - 含意：「コンテキスト経由でしか規定できない／grounded experience なき "理解" は人間のそれと別物」へ自然拡張。

6. **収束する表現（Universal）と、その反例 — 最重要・要監視**
   - Platonic Representation Hypothesis (Huh, Cheung, Wang, Isola; ICML 2024) — モデル横断の収束。意味のモデル間記述/永続化の前提。
   - **2025 反例（戦略会話より）**：weight decay / saddle points / finite-step "edge of stability" 等の条件下で収束が崩れる報告。→ **タスク**：反例条件 と Sens 対象ドメインの関係を明示し、PRH への依存をヘッジした記述に作り替える（Tier B の通過条件）。
   - 注：反例の正式書誌は未確定。本メモでは「公開された反例群が存在する」事実のみ確定扱いとし、個別引用は後工程で照合。

7. **解釈可能性 / sparse autoencoder 系譜（一般的公刊手法として）**
   - mechanistic interpretability / SAE / causal abstraction の公開研究系譜（Olah ら、Bricken/Templeton、Nanda、Sharkey、Bau、Geva、Belinkov、Geiger 等）。
   - 用法：「内部に流れるものは原理的に不可視ではない」を支える**外部の公開成果**としてのみ言及。内部実装・実験・数値へは接続しない（機密ゲート）。

8. **隣接領域（背景厚みづけ用、深入りしない）**
   - 概念空間/意味の幾何学：Gärdenfors（conceptual spaces）。
   - 情報の哲学：Floridi。
   - conceptual engineering / semantic drift；contextualism vs semantic minimalism：Travis / Recanati ／ Cappelen（対立軸）。
   - 知識グラフ/オントロジー：Vrandečić（Wikidata）。
   - 可視化：Wattenberg / Viégas。
   - **日本語圏ハブ**：Heinzerling / 横井祥 / 小林悟郎（SAE・mech interp の日本語圏翻訳）、乾健太郎、鈴木潤。日本語版の学術ポジショニングの足場。

> 注（境界）：戦略スレッドで作成された「researcher map」には競合/接触戦略の注釈が含まれる。本 §C は**公刊文献の足場のみ**を抽出し、競合・接触戦略は持ち込まない（それは maintainer 側の保持物）。

## 4. 継承後の連動

- Research 継承確認後、Papers が `_research-and-direction.md` §C をポインタ化
  （「研究プロセスの正典は Research `papers-draft/q3-extended-prh/`」と明記）
- glossary §2 (モダリティ非依存 Feature / 共有埋め込み空間) の研究 status は
  RT-B (マルチモーダル) 進行に連動して Research から更新通知 (Papers §6.2 整合)
- Gärdenfors 数学的 framework (Papers M-2 予備評価「最有望」) は Research が継承・
  深化 (research-notes/gardenfors/ + ADR-043 research basis)。Papers は公開発信時の
  引用整合のみ

## 5. dispatch メタ
- 応答期待: Research → 継承完了通知 (`dispatch/outgoing/papers/`) → Papers §C ポインタ化
- 連動: `alignment/with-papers-output.md` v0.2 改訂 (Research 予告)
