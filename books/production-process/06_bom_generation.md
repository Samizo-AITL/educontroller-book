---
title: "06_bom_generation"
---

---

# 06_bom_generation

**部品表（BOM）の作成と設計情報の構造化**  
*Bill of Materials (BOM) Generation and Structured Design Data*

---

## 🔗 公式リンク | Official Links

| 言語 / Language | GitHub Pages 🌐 | GitHub 💻 |
|-----------------|----------------|-----------|
| 🇯🇵 Japanese | [![GitHub Pages JP](https://img.shields.io/badge/GitHub%20Pages-日本語版-brightgreen?logo=github)](https://samizo-aitl.github.io/EduMecha/08_production_process/06_bom_generation/) | [![GitHub Repo JP](https://img.shields.io/badge/GitHub-日本語版-blue?logo=github)](https://github.com/Samizo-AITL/EduMecha/tree/main/08_production_process/06_bom_generation) |

---

## 📑 目次 | Table of Contents

| # | 日本語 | English | Link |
|---|--------|---------|------|
| 1 | 📘 概要 | Overview | [overview](https://samizo-aitl.github.io/EduMecha/08_production_process/06_bom_generation/overview.html) |
| 2 | 🔢 部品コード体系 | Part Numbering System | [part_numbering](https://samizo-aitl.github.io/EduMecha/08_production_process/06_bom_generation/part_numbering.html) |
| 3 | 📎 属性と輸出管理 | Attributes & Export Control | [attributes](https://samizo-aitl.github.io/EduMecha/08_production_process/06_bom_generation/attributes.html) |
| 4 | 📊 積み上げ管理 | Roll-up Management | [rollup_management](https://samizo-aitl.github.io/EduMecha/08_production_process/06_bom_generation/rollup_management.html) |
| 5 | ⚖️ 運用ルール | Rules | [rules](https://samizo-aitl.github.io/EduMecha/08_production_process/06_bom_generation/rules.html) |
| 6 | 🧪 演習課題 | Exercises | [exercises](https://samizo-aitl.github.io/EduMecha/08_production_process/06_bom_generation/exercises.html) |

---

## 📘 概要 | Overview
部品コード（6桁＋枝番）は **決まったルールに基づいて体系的に管理**されています。  
*Part codes (6 digits + suffix) are systematically managed according to defined rules.*  

コードを見れば大カテゴリ（機械・電子・材料・治具）、条件差（金型・製造地・改版）、さらに安全規制や輸出対応の要否まで追跡できます。  
*The code indicates major categories (mechanical, electronic, materials, jigs), condition differences (mold, production site, revision), and tracks regulatory and export requirements.*  

このセクションでは、設計構成に基づいた**部品表（BOM: Bill of Materials）**を作成し、量産や在庫管理に必要な構成情報を整理します。  
*This section covers creating the Bill of Materials (BOM) based on design structure, organizing essential data for mass production and inventory management.*  

BOMは単なる部品リストではなく、**設計〜調達〜生産〜輸出までをつなぐ共通言語**です。  
*A BOM is not just a list of parts, but a common language connecting design, procurement, production, and export.*  

---

## 🧑‍🏫 学習目標 | Learning Objectives
- 部品コードのルール（6桁＋枝番）を理解する  
  *Understand the rules of part coding (6 digits + suffix).*  
- 組立構造に対応した部品階層と親子関係を整理する  
  *Organize part hierarchy and parent-child relations for assemblies.*  
- 図面・環境・コスト・輸出判定を部品コードに紐づける  
  *Link drawings, environmental, cost, and export control data to part codes.*  
- 積み上げ管理（コスト・環境・輸出可否）の考え方を学ぶ  
  *Learn roll-up management for cost, environmental, and export compliance.*  
- 危険物（材料6番コード）の特別管理を理解する  
  *Understand special management for hazardous materials (category code 6).*

---

[🔝 08_production_process/README.mdに戻る ](https://samizo-aitl.github.io/EduMecha/08_production_process)
