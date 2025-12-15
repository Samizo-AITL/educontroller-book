---
title: "07_design_review"
---

# 07_design_review

**設計レビュー資料とチェックリスト管理**  
**Design Review Documents and Checklist Management**

---

## 🔗 公式リンク | Official Links

| 言語 / Language | GitHub Pages 🌐 | GitHub 💻 |
|-----------------|----------------|-----------|
| 🇯🇵 Japanese | [![GitHub Pages JP](https://img.shields.io/badge/GitHub%20Pages-日本語版-brightgreen?logo=github)](https://samizo-aitl.github.io/EduMecha/08_production_process/07_design_review/) | [![GitHub Repo JP](https://img.shields.io/badge/GitHub-日本語版-blue?logo=github)](https://github.com/Samizo-AITL/EduMecha/tree/main/08_production_process/07_design_review) |

---

## 📘 概要 | Overview

このセクションでは、製品設計の各段階で行う**設計レビュー（DR）**の準備と実施方法を学びます。  
チェックリストによる網羅確認、議事録の整理、関係者間の合意形成など、**設計の信頼性と透明性を高めるための文書化手法**を習得します。

In this section, learners prepare and conduct design reviews using structured checklists, meeting records, and review comments.  
This process enhances design quality, traceability, and team communication across engineering phases.

---

## 🧑‍🏫 学習目標 | Learning Objectives

- 設計ミスや抜け漏れを防ぐためのDRチェックリストを活用する  
- モデル・図面・BOM等に対する確認ポイントを明確化する  
- 議事録・指摘事項を文書として残す習慣を身につける  
- 意見の記録と設計変更管理の基礎を理解する  
- チーム内合意形成・意思決定を可視化する方法を学ぶ  

---

## 📂 サブディレクトリ構成 | Subdirectories

```text
07_design_review/
├── dr_checklists/            # DR用チェックリスト（部門別・段階別）
├── meeting_minutes/          # 議事録テンプレートと記入例
├── review_comments/          # 指摘事項と改善履歴
└── approval_records/         # 承認フローと署名記録（任意）
```

---


## 📝 添付ファイル一覧 | Planned Files (後で作図予定)

| ファイル名 | 内容 | 備考 |
|------------|------|------|
| `dr_checklist_general.md` | 汎用設計レビュー用チェックリスト | 教材内文書 |
| `drawing_review_checklist.md` | 製図専用の確認項目 | `02_drawing_creation/`と共用 |
| `dr_minutes_template.md` | 議事録テンプレート | Markdown形式 |
| `dr_feedback_log.md` | 指摘事項と改善履歴の記録 | 〃 |

---

## 🔗 関連セクション | Related Sections

- [`04_measurement_report/`](../04_measurement_report/)  
  → 実測差異のDR反映・レビュー対象
- [`05_production_drawing/`](../05_production_drawing/)  
  → 図面の完成度をDRで確認・承認
- [`08_mp_guideline/`](../08_mp_guideline/)  
  → DRの履歴を量産体制設計に活用

---

## 💬 コメント・共有 | Feedback

教育現場や現場設計でのDR運用例、改善アイデア、部門別チェックポイントの共有などがあれば、[Discussions](https://github.com/Samizo-AITL/EduMecha/discussions) にてぜひご参加ください。

We welcome your real-world DR practices, review strategies, and improvement experiences!
