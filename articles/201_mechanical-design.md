---
title: "【機械設計】Full Code Mechanical Design｜Pythonで機械設計を完全再現可能にする思想と実装"
emoji: "🛠️"
type: "tech"
topics: ["機械設計", "Python", "CAD", "FreeCAD", "設計自動化"]
published: true
---

# Full Code Mechanical Design とは何か

同じ形状の治具を寸法違いで量産する。
パラメータを少し変えたいだけなのに、CAD操作を最初からやり直す。

そんな経験はありませんか？

Full Code Mechanical Design（FCMD）は、
そうした機械設計の非効率を根本から解消するための
「設計をコードとして定義する」設計思想です。

---

## 設計とは本来、何を保持すべきか

設計とは本来、

・寸法  
・拘束条件  
・構造意図  
・再利用ルール  

を論理として保持すべきものです。

しかし GUI CAD では、それらの多くが
操作履歴や人の記憶に依存してしまいます。

FCMD はこれらを
Pythonコードとして完全に表現・再実行可能にします。

---

## なぜ GUI CAD では不十分なのか

GUI CAD には次のような制約があります。

・操作手順が人依存で再現できない  
・設計意図がファイルに残らない  
・寸法変更が局所的で破綻しやすい  
・自動生成・最適化が困難  

つまり GUI CAD は
「形状は残るが、設計は残らない」のです。

---

## Full Code Mechanical Design の基本原則

### 1 設計はコードで定義する

shaft_diameter = 10.0  # mm  
shaft_length   = 50.0  # mm  

寸法は GUI 操作ではなく変数です。

---

### 2 形状はロジックで生成する

import Part

shaft = Part.makeCylinder(
    shaft_diameter / 2,
    shaft_length
)

円柱・穴・面取りは
関数呼び出し＝設計意図になります。

---

### 3 パラメトリック設計は自動的に成立する

def make_shaft(d, l):
    return Part.makeCylinder(d / 2, l)

・寸法変更 → 再実行  
・設計ミス → コードレビューで検出  
・再利用 → 関数化で即対応  

特別な設定は不要です。

---

## FreeCAD + Python を採用する理由

FCMD では FreeCAD + Python を採用します。

・公式 Python API  
・ソリッド演算がスクリプトで完結  
・オープンソースで再現性が高い  
・CI / 自動生成と相性が良い  

GUI は結果確認のためのビューアに過ぎません。

---

## GUI CAD と FCMD の決定的な違い

再現性：GUI CAD 低い / FCMD 完全再現可能  
設計意図：GUI CAD 人依存 / FCMD コードに保存  
自動化：GUI CAD 困難 / FCMD 前提設計  
最適化：GUI CAD 手作業 / FCMD アルゴリズム化可能  

---

## 実務での適用例

・治具設計の自動生成  
・寸法系列の一括展開  
・設計テンプレート化  
・設計ルールのコード化  
・FEM / 制御モデルとの直結  

同系統部品を量産設計する現場では特に強力です。

---

## Full Code Mechanical Design の思想的価値

FCMD は単なる CAD テクニックではありません。

・設計＝知識資産  
・図面＝副生成物  
・コード＝設計そのもの  

という設計哲学の転換です。

---

## 参考リンク

https://samizo-aitl.github.io/full-code-mechanical-design/  
https://github.com/Samizo-AITL/full-code-mechanical-design  

---

## まとめ

GUI CAD に慣れた人ほど最初は違和感があります。
しかし一度 FCMD に移行すると、こう思うはずです。

なぜ今まで設計をコードにしなかったのか

設計を、再現可能な知識に変える。
それが Full Code Mechanical Design です。
