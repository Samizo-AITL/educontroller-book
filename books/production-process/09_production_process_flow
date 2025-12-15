---
layout: default
title: 設計から量産部品発注までの実務フロー | Design to Mass Production Flow
---

---

# 🏭 設計から量産部品発注までの一般的なフロー  
*General Workflow: From Design to Mass Production Parts Ordering*

> **注記｜Notice**  
> 本資料は、製造業において広く見られる一般的な実務フローを教育用に抽象化したものであり、特定企業の社内情報や機密情報は含みません。  
> *This material abstracts a workflow commonly observed in manufacturing industries for educational purposes. It does not contain any proprietary or internal company information.*

---

## 🔗 公式リンク | Official Links

| 言語 / Language | GitHub Pages 🌐 | GitHub 💻 |
|-----------------|----------------|-----------|
| 🇯🇵 Japanese | [![GitHub Pages JP](https://img.shields.io/badge/GitHub%20Pages-日本語版-brightgreen?logo=github)](https://samizo-aitl.github.io/EduMecha/08_production_process/09_production_process_flow/) | [![GitHub Repo JP](https://img.shields.io/badge/GitHub-日本語版-blue?logo=github)](https://github.com/Samizo-AITL/EduMecha/tree/main/08_production_process/09_production_process_flow) |

---

## 📘 概要 | Overview
本資料は、設計段階から量産部品発注に至るまでの **一般的な製造業の実務プロセス** を体系的に整理したものです。  
*This document systematically organizes a general workflow in manufacturing industries, from design to mass-production parts ordering.*

「設計図面検討」「技術図面レビュー」「関係部署への通知と配布」「BOM（部品表）との連携」「量産部品の発注」といったステップを網羅します。  
*It covers steps such as design drawing reviews, technical drawing discussions, notices and distribution to related departments, BOM (Bill of Materials) linkage, and ordering of mass-production parts.*

---

## 🔁 実務ワークフロー | Practical Workflow

```mermaid
flowchart TD
  %% 設計フロー
  A["設計図面検討会 / Design Drawing Review"] --> B["設計図面 / Design Drawing"]
  B --> C["設計通知 / Design Notice"]

  %% 技術フロー
  C --> D["技術図面検討会 / Technical Drawing Review"]
  D --> E["技術図面(加工図面・組図) / Technical Drawings"]
  E --> F["技術通知 / Technical Notice"]
  F --> G["関係部署配布 / Distribution to Departments"]
  G --> H["構成部品表接続 / BOM Linkage"]

  %% 評価・積み上げ
  H --> H1["環境データ積み上げ判定 (EChemSkip) / Environmental Compliance Check"]
  H --> H2["コスト積み上げ / Cost Roll-up"]
  H1 --> I["構成部品表通知 / BOM Notice"]
  H2 --> I
  I --> J["関係部署配布(BOM) / Distribution (BOM)"]

  %% 調達フロー
  J --> K["調達BOM反映 / Procurement BOM Integration"]
  K --> L["量産部品発注 / Mass Production Parts Ordering"]

  %% 属性群
  S1["属性(設計時必須) / Design-time Attributes
  - 図面番号/Rev
  - RoHS/REACH, LCA, SDS
  - コスト(基礎)"] -.-> H

  S2["属性(輸出時追加) / Export-time Attributes
  - 輸出管理(ECCN)
  - 該非判定(Result of Export Control Classification)
  - HSコード
  - 用途説明書(End-use Statement)"] -.-> K

  %% 横から加わる評価・計測情報
  P1["試作評価 / Prototype Evaluation\n(寸法測定・性能検証)"] -.-> B
  P2["量産評価 / Mass Production Evaluation\n(工程能力 Cp/Cpk, 品質検証)"] -.-> E
  P3["計測器情報 / Measurement Instruments\n(三次元測定機, マイクロメータ, 真円度計 等)"] -.-> E

  %% 色分けスタイル
  %% 設計（青系）
  style A fill:#d1e9ff,stroke:#0366d6,stroke-width:2px
  style B fill:#d1e9ff,stroke:#0366d6,stroke-width:2px
  style C fill:#d1e9ff,stroke:#0366d6,stroke-width:2px

  %% 技術（オレンジ系）
  style D fill:#fff3cd,stroke:#ff9900,stroke-width:2px
  style E fill:#fff3cd,stroke:#ff9900,stroke-width:2px
  style F fill:#fff3cd,stroke:#ff9900,stroke-width:2px
  style G fill:#fff3cd,stroke:#ff9900,stroke-width:2px
  style H fill:#fff3cd,stroke:#ff9900,stroke-width:2px
  style H1 fill:#fff3cd,stroke:#ff9900,stroke-width:2px
  style H2 fill:#fff3cd,stroke:#ff9900,stroke-width:2px
  style I fill:#fff3cd,stroke:#ff9900,stroke-width:2px
  style J fill:#fff3cd,stroke:#ff9900,stroke-width:2px

  %% 調達（緑系）
  style K fill:#e6ffed,stroke:#28a745,stroke-width:2px
  style L fill:#e6ffed,stroke:#28a745,stroke-width:2px

  %% 属性群（灰色系）
  style S1 fill:#f0f0f0,stroke:#666,stroke-width:1.5px
  style S2 fill:#f0f0f0,stroke:#666,stroke-width:1.5px

  %% 評価・計測情報（薄紫系）
  style P1 fill:#f5e6ff,stroke:#9b59b6,stroke-width:1.5px
  style P2 fill:#f5e6ff,stroke:#9b59b6,stroke-width:1.5px
  style P3 fill:#f5e6ff,stroke:#9b59b6,stroke-width:1.5px
```

---

## 📂 プロセス説明 | Process Description

- **設計図面検討会 → 設計図面**  
  設計意図・仕様をレビューし、正式な設計図面を確定。  
  *Review design intent/specs and finalize the design drawing.*

- **設計通知 → 技術図面検討会**  
  設計図面を通知した上で、加工図面や組立図面に展開。  
  *Issue a design notice, then develop machining and assembly drawings.*

- **技術通知 → 関係部署配布**  
  加工・組立・品質保証・SCM部門に技術情報を共有。  
  *Distribute technical information to manufacturing, assembly, QA, and SCM.*

- **構成部品表接続 → 環境判定・コスト積上 → 構成部品表通知 → 部署配布**  
  BOMに反映し、適合性とコストを確認後、関係部署へ通知・配布。  
  *Link BOM, verify environmental compliance and cost roll-up, then notify and distribute to stakeholders.*

- **調達BOM反映 → 量産部品発注**  
  調達部門が量産用のBOMを基に、部品をサプライヤへ発注。  
  *Procurement updates the purchasing BOM and places orders for mass-production parts.*

- **（輸出が必要な場合）輸出関連属性の付与**  
  ECCN・該非判定・HSコード・用途説明書を付与。  
  *If export is required, add ECCN, export classification result, HS code, and end-use statement.*

---

## 🔗 関連教材リンク | Related Materials

本実務フローに関連して、**部品表（BOM）の生成**や**設計情報の構造化**を扱った教材も公開しています。  
In relation to this workflow, teaching materials on **BOM generation** and **structured design information** are also available.  

- [BOM生成と設計情報の構造化 / BOM Generation and Structured Design Information ›](https://samizo-aitl.github.io/EduMecha/08_production_process/06_bom_generation/)

---

## 👤 著作・ライセンス | Author & License
- ✍️ 著作 / Author: **三溝真一（Samizo-AITL）**  
  *Author: Shinichi Samizo (Samizo-AITL)*  
- 📜 ライセンス / License: **MIT（教育目的での使用・改変を歓迎）**  
  *MIT License (free use and modification for educational purposes).*

---

[🔝 トップに戻る / Back to top](../)

