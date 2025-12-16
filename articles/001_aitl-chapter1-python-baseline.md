---
title: "【AITL】AITL Silicon Pathway 入門：Chapter 1（Python Baseline Model）"
emoji: "🚀"
type: "tech"
topics: ["aitl", "python", "control", "pid", "fsm", "asic"]
---

# 🚀 AITL Silicon Pathway  
## **Python → RTL → GDSII へ向かう“シリコンへの道”**  
本記事は、AITL Silicon Pathway プロジェクトの「Chapter1（Python 制御モデル）」の解説です。

---

# 🔗 **公式 GitHub Repository（コード・図・教材フルセット）**

📂 **AITL Silicon Pathway — GitHub**  
➡ https://github.com/Samizo-AITL/aitl-silicon-pathway

※記事では概要を扱い、**実行可能コード・図・教材はすべて GitHub に集約**しています。

---

# 🎯 AITL Silicon Pathway とは？

AITL（AI × Intelligent × Layered）アーキテクチャは、

**PID（制御） × FSM（状態管理） × LLM（最適化）**

の三層で構成される **ハイブリッド制御モデル** です。

本プロジェクトは、これを **Python → Verilog → OpenLane → GDSII → SPICE**  
という形で、実際に“シリコンに落とすまで”を体系的に扱う教育ロードマップです。

---

# 🧩 Chapter1 の目的

本章では、AITL の三層アーキテクチャを **Python で再構築し、動作するゴールデンモデル** を作ります。

これが後の工程、

- Verilog RTL（Chapter2）  
- OpenLane 合成 → 配置配線（Chapter3）  
- Layout→SPICE 抽出（Chapter4）  
- 物理波形解析（Chapter5）

のすべての理論的基準となります。

---

# 🏛 AITL 三層アーキテクチャ（概念図）

<img src="https://raw.githubusercontent.com/Samizo-AITL/aitl-silicon-pathway/main/docs/chapter1/images/aitl_3layer.png" width="80%">

**PID（制御）** … 目標値に対して値を収束  
**FSM（状態機械）** … システムの状態遷移を管理  
**LLM（知能層）** … パラメータ最適化・異常検知  

三者が役割分担して動作することで、  
「安定 × 適応 × 自律」を実現します。

---

# ⚙️ Chapter1 Python モデル構成

```
chapter1_python_model/
├── src/
│   ├── pid.py
│   ├── fsm.py
│   ├── aitl_controller.py
│   └── llm_placeholder.py
├── sim/
│   ├── run_step_response.py
│   └── run_fault_scenario.py
├── plots/
└── main.py
```

---

# 🧪 Step Response（ステップ応答）

<img src="https://raw.githubusercontent.com/Samizo-AITL/aitl-silicon-pathway/main/docs/chapter1/images/step_response_timeline.png" width="80%">

PID が対象値へ収束し、FSM が `RUN` 状態のまま動作する様子が分かる。

---

# 🔥 Fault Scenario（異常シナリオ）

<img src="https://raw.githubusercontent.com/Samizo-AITL/aitl-silicon-pathway/main/docs/chapter1/images/fault_timeline.png" width="80%">

LLM がなくても、FSM が異常を検出して安全側に回避する流れが見える。

---

# 🧠 FSM の状態遷移

<img src="https://raw.githubusercontent.com/Samizo-AITL/aitl-silicon-pathway/main/docs/chapter1/images/fsm_state_diagram.png" width="70%">

---

# 🛠 Controller データフロー

<img src="https://raw.githubusercontent.com/Samizo-AITL/aitl-silicon-pathway/main/docs/chapter1/images/controller_data_flow.png" width="80%">

---

# 💻 実行方法

```
cd chapter1_python_model
pip install -r requirements.txt
python main.py
```

---

# 🔜 次章（Chapter2）：FSM を Verilog RTL に落とす

Chapter2 では、

- Python FSM の仕様
- Moore/Moore 型ステートマシンの整理
- Verilog RTL への翻訳
- RTL シミュレーション（iverilog）
- テストベクタ生成方法

など、ASIC 実装への第一歩を解説します。

今後の Zenn 記事はこの順に公開していきます。

---

# 📎 GitHub Repository（総合リンク）

記事で紹介したコード・図・教材すべて：  
➡ https://github.com/Samizo-AITL/aitl-silicon-pathway

---

# 📝 おわりに

このシリーズは、「Python の制御モデルをそのまま ASIC に落とす」という、  
国内でも例のない実践型教材を目指しています。

---

# 💬 フィードバック

質問・改善提案は GitHub Discussions へ  
➡ https://github.com/Samizo-AITL/aitl-silicon-pathway/discussions

