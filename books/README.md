# 📚 Zenn Books Directory

このディレクトリ `books/` には、Zenn で公開する複数の書籍プロジェクトをまとめて管理しています。  
各フォルダが 1 冊の書籍として構成され、Zenn の GitHub 連携により自動的に書籍として認識されます。

---

# 📘 書籍一覧

## 1. **EduController**
制御工学を古典 → 現代 → デジタル → 適応 → AI まで体系的に学べる統合教材。

📂 フォルダ：`books/educontroller`  
📄 概要：PID、状態空間、デジタル制御、MRAC、NN制御、RL制御、SoC制御など幅広い内容を収録。

---

## 2. **EduSemi-v4x**
半導体工学の基礎（物性・デバイス・プロセス・設計）を体系的にまとめた教材。

📂 フォルダ：`books/edusemi-v4x`  
📄 概要：MOSFET、CMOSプロセス、材料物性、回路設計など半導体の基礎を整理。

---

## 3. **EduSemi-Plus**
半導体応用・地政学・AI時代の製造戦略など、応用領域を扱う拡張教材。

📂 フォルダ：`books/edusemi-ples`  
📄 概要：半導体産業の歴史、AIと製造、国際競争力、産業政策などを扱う。

---

# 📁 ディレクトリ構造

```

books/
├ educontroller/
│ ├ config.yaml
│ ├ cover.png (任意)
│ ├ 01_xxx.md
│ ├ 02_xxx.md
│ └ ...
│
├ edusemi-v4x/
│ ├ config.yaml
│ ├ cover.png
│ ├ 01_xxx.md
│ └ ...
│
└ edusemi-ples/
├ config.yaml
├ cover.png
├ 01_xxx.md
└ ...

```

---

# 📌 Zenn 書籍の構築ルール（重要）

Zenn に書籍として認識させるためには、以下の仕様に従う必要があります：

### ✔ 書籍フォルダ直下に `.md` を置く  
サブフォルダ（`chapters/` など）は使用できません。

### ✔ `config.yaml` の chapters: で順順を指定  
例：
```
yaml
chapters:
  - 01_intro
  - 02_theory
  - 03_application
```

## ✔ cover.png は任意で配置可能
表紙として表示されます。

## ✔ GitHub → Zenn の連携はリポジトリ単位
zenn-books リポジトリ全体を 1 回連携すれば  
books/ 内のすべての書籍が自動的に認識されます。

---

## 🚀 デプロイの流れ

1. このリポジトリ（zenn-books）を Zenn と連携  
2. 書籍フォルダを自動検出  
3. .md を更新して push  
4. Zenn で自動ビルド  
5. 書籍内容が即反映される  

---

## 👤 Author
Samizo-AITL  
AI × 制御 × 半導体 技術教育プロジェクト


