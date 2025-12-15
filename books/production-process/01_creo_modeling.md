# 01_creo_modeling

**パラメトリック設計のためのCreoモデリング入門**  
**Introduction to Parametric Modeling with Creo**

---

## 🔗 公式リンク | Official Links

| 言語 / Language | GitHub Pages 🌐 | GitHub 💻 |
|-----------------|----------------|-----------|
| 🇯🇵 Japanese | [![GitHub Pages JP](https://img.shields.io/badge/GitHub%20Pages-日本語版-brightgreen?logo=github)](https://samizo-aitl.github.io/EduMecha/08_production_process/01_creo_modeling/) | [![GitHub Repo JP](https://img.shields.io/badge/GitHub-日本語版-blue?logo=github)](https://github.com/Samizo-AITL/EduMecha/tree/main/08_production_process/01_creo_modeling) |

---

## 📘 概要 | Overview

このセクションでは、PTC Creo Parametricを使用して、基本的な3Dモデリング手法とパラメトリック設計の考え方を学びます。  
スケッチ拘束、寸法パラメータ、モデル履歴の操作など、後工程（図面化・試作・量産）にもつながる**設計意図の明示**を重視した基礎演習です。

In this section, learners will explore foundational 3D modeling techniques in PTC Creo Parametric, focusing on parametric constraints, dimensions, and modeling intent.  
The goal is to build reusable, editable designs that form the basis for downstream tasks such as drawing, prototyping, and production.

---

## 🧑‍🏫 学習目標 | Learning Objectives

- Creoの基本操作（UI、ファイル保存、モデル操作）に慣れる  
- スケッチ拘束と幾何関係（水平・垂直・対称など）を理解する  
- 寸法・パラメータを使ったモデル制御を習得する  
- フィーチャーの順序と履歴ツリーを活用する  
- 「設計意図」の伝わるモデル構築法を実践する  

---

## 📂 サブディレクトリ構成 | Subdirectories

```text
01_creo_modeling/
├── basic_sketch/           # スケッチ拘束と形状の基本
├── extrusion_practice/     # 押し出し・回転・除去の操作練習
├── parametric_modeling/    # 寸法変数・パラメトリック制御
└── example_models/         # 教材用サンプルモデル（.prt, .asm）
```

---

## 📝 添付ファイル一覧 | Planned Files (後で作図予定)

| ファイル名 | 内容 | 備考 |
|------------|------|------|
| `sketch_block.prt` | 基本スケッチ（矩形・拘束付き） | Creoモデル（予定） |
| `cylinder_cut.prt` | 押し出し・除去・フィレット練習 | 〃 |
| `parametric_box.prt` | 寸法変数による再利用可能モデル | 〃 |
| `parametric_design_checklist.md` | 設計意図チェックリスト | 教材内文書 |

※モデルは後で作図リストとしてまとめます。

---

## 🔗 関連セクション | Related Sections

- [`02_drawing_creation/`](../02_drawing_creation/)  
  → モデリング結果をもとに2D設計図面を作成
- [`05_production_drawing/`](../05_production_drawing/)  
  → パラメータ・公差を含む製図との連携
- [`08_mp_guideline/`](../08_mp_guideline/)  
  → 設計履歴・意図の共有を前提とした構成管理

---

## 💬 コメント・共有 | Feedback

ファイル構成や学習順の改善案、学生演習での使用例などがありましたらぜひ [Discussions](https://github.com/Samizo-AITL/EduMecha/discussions) にて共有ください。

We welcome your feedback or use cases via Discussions. Feel free to contribute ideas or improvements!
