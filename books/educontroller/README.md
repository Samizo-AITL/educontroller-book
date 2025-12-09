# 📘 EduController — 統合制御工学テキスト

本フォルダは Zenn 上で公開する書籍 **「EduController」** のソースです。  
古典制御から AI 制御まで、制御工学を体系的に整理した教材として構成しています。

---

# 📂 構成

```

books/educontroller/
├ config.yaml
├ cover.png
├ 01_classical.md
├ 02_modern.md
├ 03_digital.md
├ 04_adaptive.md
├ 05_practical.md
├ 06_nn_control.md
├ 07_rl_control.md
├ 08_data_driven.md
├ 09_llm_hybrid.md
├ 10_pendulum.md
├ 11_matlab_tools.md
└ 12_soc_designkit.md

```

---

# 📝 config.yaml の役割

Zenn における書籍のメタ情報と、章の順序を定義します。

```yaml
title: "EduController"
summary: "古典・現代・デジタル・適応・AI制御まで体系的に学べる統合教材"
topics:
  - control
  - pid
  - robotics
  - engineering
published: false

chapters:
  - 01_classical
  - 02_modern
  - 03_digital
  - 04_adaptive
  - 05_practical
  - 06_nn_control
  - 07_rl_control
  - 08_data_driven
  - 09_llm_hybrid
  - 10_pendulum
  - 11_matlab_tools
  - 12_soc_designkit

```
