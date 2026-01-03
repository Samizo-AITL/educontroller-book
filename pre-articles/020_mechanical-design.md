---
title: "【機械設計】Full Code Mechanical Design｜Pythonで機械設計を完全再現可能にする思想と実装"
emoji: "🛠️"
type: "tech"
topics: ["機械設計", "Python", "CAD", "FreeCAD", "設計自動化"]
published: true
---

# Full Code Mechanical Design とは何か

**Full Code Mechanical Design（FCMD）** とは、  
従来の GUI 主体の CAD 設計から脱却し、  
**機械設計そのものをコードで定義・再現・自動生成する** という設計思想です。

設計とは本来、

- 寸法
- 拘束条件
- 構造意図
- 再利用ルール

を **論理として保持** すべきものです。  
FCMD はそれを **Pythonコードとして完全に表現** します。

---

## なぜ GUI CAD では不十分なのか

GUI CAD には以下の致命的な制約があります。

- 操作履歴が「人依存」で再現できない
- 設計意図がファイルに残らない
- パラメータ変更が局所的で破綻しやすい
- 設計の自動生成・最適化が困難

つまり GUI CAD は  
**「図面は残るが、設計思想は残らない」** のです。

---

## Full Code Mechanical Design の基本原則

FCMD は次の原則で構成されます。

### 1️⃣ 設計はコードで定義する

```python
shaft_diameter = 10.0  # mm
shaft_length   = 50.0  # mm
```

寸法は GUI 操作ではなく **変数** として定義します。

---

### 2️⃣ 形状はロジックで生成する

```python
import Part

shaft = Part.makeCylinder(
    shaft_diameter / 2,
    shaft_length
)
```

円柱・穴・面取りは  
**関数呼び出し＝設計意図** です。

---

### 3️⃣ パラメトリック設計が自動的に成立する

```python
def make_shaft(d, l):
    return Part.makeCylinder(d/2, l)
```

- 寸法変更 → 再実行
- 設計ミス → コードレビューで検出
- 再利用 → 関数化で即対応

---

## FreeCAD + Python を採用する理由

FCMD では **FreeCAD** を採用します。

理由は明確です。

- Python API が公式に提供されている
- ソリッド演算がスクリプトで完結する
- オープンソースで再現性が高い
- CI / 自動生成と相性が良い

GUI は **結果の可視化ツール** に過ぎません。

---

## GUI CAD と FCMD の決定的差分

| 項目 | GUI CAD | FCMD |
|----|----|----|
| 再現性 | 低い | **完全再現可能** |
| 設計意図 | 人依存 | **コードに保存** |
| 自動化 | 困難 | **前提設計** |
| 最適化 | 手作業 | **アルゴリズム化可能** |

---

## 実務での適用例

- 治具設計の自動生成
- 寸法系列の一括展開
- 設計テンプレート化
- 設計ルールのコード化
- FEM / 制御モデルとの直結

特に **「同系統部品を量産設計する現場」** では圧倒的に強力です。

---

## Full Code Mechanical Design の思想的価値

FCMD は単なる CAD テクニックではありません。

- 設計＝知識資産
- 図面＝副生成物
- コード＝設計そのもの

という **設計哲学の転換** です。

---

## 参考リンク

- Full Code Mechanical Design  
  https://samizo-aitl.github.io/full-code-mechanical-design/

- GitHub Repository  
  https://github.com/Samizo-AITL/full-code-mechanical-design

---

## まとめ

GUI CAD に慣れた人ほど最初は違和感があります。  
しかし一度 FCMD に移行すると、

> 「なぜ今まで設計をコードにしなかったのか」

と必ず思います。

**設計を、再現可能な知識に変える。**  
それが Full Code Mechanical Design です。
