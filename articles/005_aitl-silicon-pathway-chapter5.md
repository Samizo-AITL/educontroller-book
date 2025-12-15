---
title: "【AITL】Silicon Pathway Ch5：FSM正しさの動的検証"
emoji: "🧪"
type: "tech"
topics: ["fsm", "verilog", "verification", "assertion"]
published: false
---

# Chapter5 は作業章

Chapter4 は「考え方」でした。  
Chapter5 は **手を動かす章**です。

---

## やることは単純

- Invariant → assertion にする
- assertion を simulation で回す
- Python FSM と Verilog FSM を並べて比べる

---

## 重要な割り切り

- formal tool は必須ではない
- assertion は「仕様の番人」
- simulation でも多くの設計バグは潰せる

---

## FSM 検証の実務的最小セット

- 状態合法性チェック
- 遷移合法性チェック
- 出力安全性チェック
- reset チェック
- 等価性チェック

---

## Chapter5 のゴール

> 「正しいと主張した FSM が、  
>  実際にそれを破ろうとしても壊れない」

ここまで来たら、
FSM 設計としては十分に **実戦投入レベル**。
