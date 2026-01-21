---
title: "zenn-books"
description: "zenn-books"
---


# 📚 zenn-books

## 🔗 Links

| Language | GitHub Pages 🌐 | GitHub 💻 |
|----------|----------------|-----------|
| Japanese | [![GitHub Pages EN](https://img.shields.io/badge/GitHub%20Pages-Japanese-brightgreen?logo=github)](https://samizo-aitl.github.io/zenn-books/) | [![GitHub Repo EN](https://img.shields.io/badge/GitHub-Japanese-blue?logo=github)](https://github.com/Samizo-AITL/zenn-books/tree/main) |

[![Back to Samizo-AITL Portal](https://img.shields.io/badge/Back%20to%20Samizo--AITL%20Portal-brightgreen)](https://samizo-aitl.github.io) 

Zenn で公開する複数の書籍をまとめて管理するためのリポジトリです。  
以下の構成で、各書籍を `books/` ディレクトリ以下に配置しています。

```

zenn-books/
├ books/
│ ├ educontroller/
│ ├ edusemi-v4x/
│ 
└ README.md

```

## 📘 書籍一覧

### 1. **EduController**
古典制御・現代制御・デジタル制御・適応制御・AI制御を体系的に整理した統合教材。

📂 フォルダ：`books/educontroller`

---

### 2. **EduSemi-v4x**
半導体デバイス・プロセス・設計・物性の基礎理論をまとめた教材。

📂 フォルダ：`books/edusemi-v4x`

---

## 📦 Zenn へのデプロイについて

本リポジトリを Zenn と GitHub 連携することで、  
`books/*/config.yaml` を読み取り自動的に書籍として反映されます。

- 書籍フォルダ直下に `.md` が存在する必要があります  
- `config.yaml` の `chapters:` の順番で書籍が構成されます  
- サブフォルダは使用できません（Zenn仕様）

---

## 📁 ディレクトリ仕様

### books/<book-name>/
- `config.yaml`  
- `cover.png`（任意）  
- 章ファイル（例：`01_intro.md`）  

---

## 👤 Author

| 📌 Item | Details |
|--------|---------|
| **Name** | Shinichi Samizo |
| **Expertise** | Semiconductor devices (logic, memory, high-voltage mixed-signal)<br>Thin-film piezo actuators for inkjet systems<br>PrecisionCore printhead productization, BOM management, ISO training |
| **GitHub** | [![GitHub](https://img.shields.io/badge/GitHub-Samizo--AITL-blue?style=for-the-badge&logo=github)](https://github.com/Samizo-AITL) |

---

## 📄 License

[![Hybrid License](https://img.shields.io/badge/license-Hybrid-blueviolet)](https://samizo-aitl.github.io/mems-ana//#-license)

| 📌 Item | License | Description |
|--------|---------|-------------|
| **Source Code** | [**MIT License**](https://opensource.org/licenses/MIT) | Free to use, modify, and redistribute |
| **Text Materials** | [**CC BY 4.0**](https://creativecommons.org/licenses/by/4.0/) or [**CC BY-SA 4.0**](https://creativecommons.org/licenses/by-sa/4.0/) | Attribution required; share-alike applies for BY-SA |
| **Figures & Diagrams** | [**CC BY-NC 4.0**](https://creativecommons.org/licenses/by-nc/4.0/) | Non-commercial use only |
| **External References** | Follow the original license | Cite the original source properly |

