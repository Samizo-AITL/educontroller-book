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

EDA フローの紹介記事を見ていると、  
**結果が出たあとで条件が調整されているケース**も少なくありません。

そこで今回は、

> **最小限の自作RTLを「事前に宣言」した状態で OpenLane superstable を流し、  
> RTL → GDS まで本当に完走するのか**

を検証してみました。

---

## 今回やったこと（要点）

やったことは非常にシンプルです。

- 自作の **最小RTL（カウンタ）** を用意
- 制約条件を **実行前に固定**
- OpenLane **superstable を改変せず**に実行
- 成否は **「GDSが出るかどうか」だけ**で判断

性能評価や最適化は、  
**今回の検証対象には含めていません。**

---

## 「事前宣言」とは何か

今回のキーワードは **事前宣言** です。

これはツールの正式な用語ではなく、

> **結果を見る前に、  
> RTL・制約・成功条件を決めておくこと**

を意味しています。

### 事前に決めたこと

- RTLの中身（あとから変えない）
- クロック周期・util などの制約（あとからいじらない）
- 成功条件は **「GDSが出ること」だけ**

つまり、

- 「流れなかったら条件を緩める」
- 「通った設定だけを成功例として出す」

といった **後出し解釈をしない**ための約束です。

---

## 設計の中身（最小RTL）

設計は **本当に最小限**です。

| 項目 | 内容 |
|---|---|
| 機能 | フリーランニング・カウンタ |
| FSM | なし |
| クロック | 単一 |
| リセット | 同期・Low active |
| マクロ | 使用しない |

RTL は以下です。

- `rtl/spm_min_counter.v`

「この程度のRTLでも OpenLane は最後まで流れるのか？」  
を確認するための構成です。

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

## RTLシミュレーション（テストベンチ）

物理設計とは別に、  
**論理確認用の最小テストベンチ**も用意しています。

```
spm_min_counter/
├─ README.md
│
├─ rtl/                         # 設計RTL（OpenLane用・非改変）
│  └─ spm_min_counter.v
│
├─ sim/                         # 論理シミュレーション（追加）
│  ├─ tb_spm_min_counter.v      # テストベンチ
│  ├─ run.sh                    # iverilog + GTKWave 実行スクリプト
│  └─ wave/                     # VCD 出力（生成物）
│     └─ spm_min_counter.vcd
│
├─ openlane/                    # OpenLane 設定
│  └─ config.tcl
│
├─ runs/                        # OpenLane 実行結果（自動生成）
│  └─ RUN_YYYY.MM.DD_HH.MM.SS/
│     ├─ logs/
│     ├─ reports/
│     ├─ results/
│     │  └─ spm_min_counter.gds
│     ├─ tmp/
│     ├─ cmds.log
│     ├─ config.tcl
│     ├─ openlane.log
│     ├─ warnings.log
│     └─ runtime.yaml
│
├─ results/                     # 教材用に抜き出した成果物
│  ├─ spm_min_counter.gds
│  ├─ 1_overview.png
│  ├─ 2_full.png
│  ├─ 3_metal.png
│  ├─ 4_cts_clock.png
│  ├─ 5_pnd.png
│  ├─ 6_cell_density.png
│  ├─ 7_min_rtl.png
│  └─ gtkwave.png
│
└─ run_log/                     # 実行サマリ（教材参照用）
   └─ flow_summary.md

```

### テストベンチの方針

- RTL は **OpenLane用をそのまま使用**
- reset を増やすなどの **都合の良い改変はしない**
- シミュレーションでは `force / release` により
  **内部レジスタの初期化のみを行う**

これは、

> 論理確認と物理設計を混ぜない

ための意図的な設計です。

---

## GTKWave による波形確認

GTKWave で確認した波形が以下です。

- `clk`：100MHz でトグル
- 内部レジスタ `cnt[23:0]`：クロック立上りごとにインクリメント
- 初期 X 状態が解消されていることを確認

<p align="center">
  <img
    src="https://raw.githubusercontent.com/Samizo-AITL/SemiDevKit/main/openlane/openlane-superstable/spm_min_counter/results/gtkwave.png"
    alt="GTKWave waveform spm_min_counter"
    style="width:80%; height:auto;"
  >
</p>

ここで **論理として正しく動作していること**を確認してから  
OpenLane に流しています。

---

## OpenLane 実行結果

結果は以下の通りです。

- RTL → GDS：✅ 完走
- CTS：問題なし
- ルーティング：致命的な詰まりなし
- DRC / LVS：OpenLane 標準チェックをパス

成果物：

- GDS  
  `results/spm_min_counter.gds`
- 実行サマリ  
  `run_log/flow_summary.md`

---

## レイアウトの見え方（KLayout）

KLayout での結果を **PNG として保存**しています。

- `1_overview.png`：全体配置
- `3_metal.png`：配線
- `4_cts_clock.png`：クロック
- `5_pnd.png`：電源
- `6_cell_density.png`：セル密度
- `7_min_rtl.png`：RTL対応

`1_overview.png`（全体配置）：

<p align="center">
  <img
    src="https://raw.githubusercontent.com/Samizo-AITL/SemiDevKit/main/openlane/openlane-superstable/spm_min_counter/results/1_overview.png"
    alt="OpenLane superstable spm_min_counter layout overview"
    style="width:80%; height:auto;"
  >
</p>

KLayout を起動しなくても、  
配置・電源・密度の雰囲気が把握できるようにしています。

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
- あとはこの基準点から、
  条件を1つずつ変えていけばよい

---

## 参考リンク

- GitHub Pages  
  https://samizo-aitl.github.io/SemiDevKit/openlane/openlane-superstable/spm_min_counter

- GitHub Repository  
  https://github.com/Samizo-AITL/SemiDevKit/tree/main/openlane/openlane-superstable/spm_min_counter

