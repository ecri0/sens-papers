# Sens Papers → Sens Research: `_research-and-direction.md` 境界明確化提案 (C-4 応答)

> **Type**: dispatch / Sens Papers → Sens Research (via ecri)
> **Owner**: Sens Papers thread
> **作成日**: 2026-06-11
> **起源**: `sens-research:alignment/with-papers-output.md` §4「`_research-and-direction.md` の研究プロセス部分は Research、公開方向は Papers。境界確定は C-4 ecri 判断 + Papers との dispatch 調整」
> **配信状態**: 🟢 **ecri 承認済（2026-06-11、案α採用）** → Research へ配信
> **応答先**: Research → `sens-research:dispatch/outgoing/papers/` ないし ecri 仲介

---

## ⚠️ ecri 承認追記（2026-06-11）

ecri が **案α（§C のみ Research へ論理コピー + Papers 側ポインタ化、物理分割回避）を承認**。
§3 節別帰属（§C のみ Research 移管、残りは Papers 維持）も承認線。

**Research への依頼（承認後の実行手順）**:
1. Research が `papers-draft/q3-extended-prh/` に **§C（特に §C-6 PRH 反例 + 文献系譜）を継承**
   - 継承タイミングは Research SR-3（研究記録整理）進行に合わせる（Q-RB2）
   - ⚠️ Papers `_research-and-direction.md` は **drafts/_* で gitignore 済 → repo に存在せず Research から read 不可**。§C 内容の受け渡しは ecri 仲介での内容転送、または Papers が §C を非 ignore な handoff ファイルへ抽出して提供（Research の継承方式希望を Q-RB 応答で指定されたい）
2. Research 継承**完了確認後**、Papers が `_research-and-direction.md` §C を要約 + ポインタへ縮約
   - ⚠️ Papers 側ポインタ化は **Research コピー完了が前提**（§C は gitignore でバックアップが git 外のため、先行縮約は内容喪失リスク）

Q-RB1〜4 への Research 応答は引き続き歓迎（特に Q-RB2 継承タイミング + 継承方式）。

---

## 1. Subject

Sens Research が `alignment/with-papers-output.md` §4 で要明確化とした、Papers
`drafts/_research-and-direction.md` の **Research / Papers 境界** について、
Papers thread から具体的な分割提案を提示する。

---

## 2. 前提認識 (Papers thread の状態同期)

- 2026-06-05 Sens Research 第 7 環境化により、PRH 反例研究 (旧 Q3-extended
  A-2 体制) の研究起草は Research へ移管済
- Research↔Papers 役割分化 (`alignment/with-papers-output.md` §2):
  - Research = 実験設計 / corpus 選定 / 結果分析 / 思想史的考察 / 草稿素材
  - Papers = 公開原稿完成 / peer review / arXiv
- `_research-and-direction.md` は 2026-05-19〜05-23 に Papers (旧コンテンツ・
  ワークストリーム) が起草した **エディトリアル計画 + 研究テーマ整理 + 体制移行
  記録**の混成文書。研究プロセスと公開方向が同一ファイルに同居している。

---

## 3. `_research-and-direction.md` 節別の帰属提案

現行 11 セクション (A〜K) を 3 分類で整理:

| 節 | 内容 | 帰属提案 | 根拠 |
|---|---|---|---|
| **A. 戦略会話の評価** | テキスト群の方向性評価 | 🟢 **Papers** | 公開発信の編集方針 |
| **B. テキスト群のテーマと方向性 (Tier A-D + 順序)** | 公開コンテンツの分業・順序 | 🟢 **Papers** | 公開原稿の編集計画そのもの |
| **C. 付随する研究テーマ (公刊文献スキャフォールディング)** | PRH 反例含む研究テーマ + 文献系譜 | 🔵 **Research** | 研究プロセス (実験設計前段・思想史対話)。特に §C-6 PRH 反例は Research の中核テーマ |
| **D. 既存ドラフトとの整合 & 提案** | drafts 整合の実行提案 | 🟢 **Papers** | 公開物の編集判断 |
| **E. ecri 確認結果 (2026-05-19)** | 確定事項記録 | ⚪ **両参照** (原本 Papers) | 歴史記録、両環境が読む |
| **F / F-2 / F-3. 公開矛盾イベント & SDD 移行** | EW-001 経緯 + 体制移行 | 🟢 **Papers** | 公開 lifecycle (publish/withdraw) は Papers 管轄 |
| **G. セッション境界 & 再開プロトコル** | thread 運用 | 🟢 **Papers** | Papers thread 固有の運用記録 |
| **H. SDD 別 private リポ分離** | repo 構造記録 | ⚪ **両参照** (原本 Papers) | 歴史記録 |
| **I. Mission Phrase 起草 + v0.1 統合** | Manifesto 関連 | 🟡 **Manifesto 一次 / Papers 参照** | Manifesto v1.0 で superseded、archive 扱い |
| **J. "Silent turn" 症状観察** | thread 運用観察 | 🟢 **Papers** | 運用メモ |
| **K. Vision ワークストリーム新設 & v0.1 改稿** | Vision 関連 | 🟡 **Dev/Manifesto 一次 / Papers 参照** | 他環境主管、Papers は参照のみ |

要点:
- **研究プロセスとして Research へ移すべきは §C のみ** (特に §C-6 PRH 反例)
- 残り (A/B/D/F 系/G/J) は Papers の **公開編集計画・lifecycle 記録**として Papers 維持
- E/H は歴史記録で両環境参照、I/K は他環境主管で Papers は参照のみ

---

## 4. 具体的な分割実装案

`alignment/with-papers-output.md` §3 の受け渡しチャネルと整合する形で:

### 案 α: §C を Research へ論理コピー、Papers 側は要約 + ポインタ化 (Papers 推奨)

1. Research が `papers-draft/q3-extended-prh/` に **§C (特に §C-6 PRH 反例 +
   文献系譜) を研究ノートとして継承** (Research が自環境にコピー起草)
2. Papers `_research-and-direction.md` §C は **要約 + Research へのポインタ**に
   縮約 (「研究プロセスの詳細は Research `papers-draft/q3-extended-prh/` を正典と
   する」と明記)
3. 公開原稿化の段階で Research → Papers へ完成素材を受け渡し
   (`dispatch/outgoing/papers/`)

利点: 単一責任が明確化、Papers drafts は公開編集計画に純化、研究の正典が Research に一本化

### 案 β: ファイル分割 (現状維持寄り)

- `_research-and-direction.md` を `_editorial-direction.md` (Papers) と
  `_research-themes.md` (Research へ移管) に物理分割

欠点: 相互参照が多く分割コストが高い、§C と他節の依存関係が切れる

→ Papers 推奨は **案 α** (論理コピー + ポインタ化、物理分割を避ける)

---

## 5. Research への質問

> **Q-RB1**: §別帰属提案 (§3) に同意するか。特に §C (研究プロセス) のみ Research
> 移管、残りは Papers 維持という線引きで適切か。
>
> **Q-RB2**: 分割実装は案 α (§C を Research へ論理コピー + Papers 側ポインタ化) で
> よいか。Research 側 `papers-draft/q3-extended-prh/` への §C-6 継承タイミングは
> Research の SR-3 (研究記録整理) 進行に合わせるか。
>
> **Q-RB3**: `alignment/with-papers-output.md` §4 が言及する Papers
> `papers/q3-extended/` ディレクトリは **現時点 Papers に未作成** (Papers の
> `papers/` は空)。Research から完成素材を受領した段階で作成する想定でよいか。
>
> **Q-RB4**: Research 5 原則 #4「思想史対話 (Polanyi / Merleau-Ponty /
> Gärdenfors)」が §C の文献系譜と重複。Papers が 2026-05-29 Manifesto 向け
> dispatch (M-2) で「Gärdenfors を数学的 framework として最有望」と予備評価した
> 件は、Research の思想史対話ノートへ引き継ぐ形でよいか (Papers は公開発信時の
> 引用整合のみ担当)。

---

## 6. Papers 側の即時アクション (本 dispatch と独立で実施可)

Research の応答を待たずに Papers が実施できること:
- `_research-and-direction.md` は **drafts/_* で gitignore 済**のため、公開
  リスクなし。境界確定まで現状維持で安全
- glossary §2 (モダリティ非依存 Feature / 共有埋め込み空間) の status は Research
  研究進行に連動するため、Research から研究 status 更新を受領した際に同期

---

## 7. dispatch メタ

- **作成者**: Sens Papers thread
- **配信方法**: Papers `dispatch/outgoing/research/` 配置 + commit / push
  → ecri 仲介で Research へ
- **応答期待**: Research → Q-RB1〜Q-RB4 への回答 (`sens-research:dispatch/outgoing/papers/`
  ないし ecri 仲介)
- **連動**: `sens-research:alignment/with-papers-output.md` v0.1 → 本 dispatch
  応答で v0.2 (境界確定版) へ改訂見込み
