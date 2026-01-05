# 📚 zenn-books

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

## 📝 ライセンス

（必要に応じて記載）

---

## 👤 Author
Samizo-AITL


