---
title: "Planar MOSFET と SCE：なぜ微細化は行き詰まったのか"
emoji: "📉"
type: "tech"
topics: ["半導体", "MOSFET", "SCE", "デバイス物理"]
published: false
---

## はじめに

MOSFET の微細化は、長い間「寸法を縮める」ことで性能向上を実現してきました。  
しかし、ある世代以降から **Short Channel Effect（SCE）** が支配的になり、
単純なスケーリングが成立しなくなります。

---

## Short Channel Effect の本質

代表的な SCE には以下があります。

- Vth roll-off
- DIBL（Drain Induced Barrier Lowering）
- サブスレッショルド特性の劣化

重要なのは、これは加工精度の問題ではなく、  
**ゲートによる電界制御能力そのものの限界**だという点です。

---

## 問題は「寸法」ではなく「電界」

ゲート長を短くしても、  
チャネル内部のポテンシャルを十分に支配できなくなった時点で、
Planar MOSFET は構造的限界に到達しました。

この課題が、次の構造変化を必然にします。
