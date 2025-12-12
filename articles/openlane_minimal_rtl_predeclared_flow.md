---
title: "OpenLane superstableを「最小RTL→GDS」で事前宣言検証してみた"　
emoji: "🧩"
type: "tech"
topics: ["OpenLane", "SKY130", "EDA", "半導体", "VLSI"]
published: true
---

## はじめに

OpenLane を触っていると、こんな疑問が出てきます。　

- 「結局、このフローは *普通のRTL* でも最後まで流れるのか？」
- 「チューニングしないとダメなんじゃないか？」
- 「成功例って、あとから条件を調整してない？」

そこで今回は、  
**最小限の自作RTLを「事前に宣言」した状態で OpenLane superstable を流し、  
RTL → GDS まで本当に完走するのか**を検証しました。

---

## 今回やったこと（要点）

- 自作の **最小RTL（カウンタ）** を用意
- 制約条件を **実行前に固定**
- OpenLane **superstable を改変せず**に実行
- 成否は「GDSが出るかどうか」だけで判断

性能や最適化は **一切評価対象にしません**。

---

## 「事前宣言」とは何か

今回のポイントは **事前宣言** です。

これはツールの用語ではなく、

> **結果を見る前に、  
> RTL・制約・成功条件を決めておくこと**

を指しています。

### 事前に決めたこと

- RTLの中身（あとから変えない）
- クロック周期・util などの制約（あとからいじらない）
- 成功条件は **「GDSが出ること」だけ**

つまり、

> 「流れなかったら条件を緩める」  
> 「通った設定だけを成功例として出す」

という **後出し解釈をしない**ための約束です。

---

## 設計の中身（最小RTL）

設計は **本当に最小**です。

| 項目 | 内容 |
|---|---|
| 機能 | フリーランニング・カウンタ |
| FSM | なし |
| クロック | 単一 |
| リセット | 同期・Low active |
| マクロ | 使用しない |

RTLはこちらです。

- `rtl/spm_min_counter.v`

「この程度のRTLでも流れるのか？」  
を確かめるための構成です。

---

## 事前に固定した制約

| 項目 | 値 |
|---|---|
| クロック周期 | 10ns（100MHz） |
| Core utilization | 30% |
| Aspect ratio | 1.0 |

設定ファイル：

- `openlane/config.tcl`

**実行後に制約を調整することはしていません。**

---

## OpenLane 実行結果

結果は以下の通りです。

- RTL → GDS：✅ 完走
- CTS：問題なし
- ルーティング：致命的な詰まりなし
- DRC / LVS：OpenLane標準チェックをパス

成果物：

- GDS  
  `results/spm_min_counter.gds`
- 実行サマリ  
  `run_log/flow_summary.md`

---

## レイアウトの見え方

KLayout での確認結果を、  
**PNGとして保存**しています。

- `1_overview.png`：全体配置
- `3_metal.png`：配線
- `4_cts_clock.png`：クロック
- `5_pnd.png`：電源
- `6_cell_density.png`：セル密度
- `7_min_rtl.png`：RTL対応

KLayoutを起動しなくても、  
「どう配置・配線されたか」が分かるようにしました。

---

## 何が分かったか

今回の検証で言えることは、とてもシンプルです。

- OpenLane superstable は  
  **自作RTL・最小構成でも RTL→GDS を完走できる**
- 「チューニングしないと流れない」という前提は  
  **少なくともこの条件では不要**
- この設計は  
  **今後の比較実験の基準点（baseline）**として使える

---

## あえてやらなかったこと

今回は、次のことを **意図的にやっていません**。

- クロックを速くする
- FSMを入れる
- データ幅を広げる
- 制約を調整する

それらは **次の検証テーマ**です。

---

## まとめ

- 「最小RTLを事前宣言して流す」ことで、
  OpenLane の成立性を客観的に確認できた
- 成功例としてではなく、
  **判断基準としての設計**を残せた
- あとはこの基準点から、条件を1つずつ変えていけばよい

---

## 参考リンク

- GitHub Pages  
  https://samizo-aitl.github.io/SemiDevKit/openlane/openlane-superstable/spm_min_counter

- GitHub Repository  
  https://github.com/Samizo-AITL/SemiDevKit/tree/main/openlane/openlane-superstable/spm_min_counter
