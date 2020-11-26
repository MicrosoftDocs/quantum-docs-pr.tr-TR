---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: Timedependentblockenkodlamaya göre Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: 8fade22dca7af16a567a88f4413c8e9dcc1604b2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203510"
---
# <a name="timedependentblockencoding-user-defined-type"></a><span data-ttu-id="7c0d1-102">Timedependentblockenkodlamaya göre Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="7c0d1-102">TimeDependentBlockEncoding user defined type</span></span>

<span data-ttu-id="7c0d1-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7c0d1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7c0d1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c0d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c0d1-105">Bir `BlockEncoding` saat kaydı tarafından denetlenen bir öğesini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="7c0d1-105">Represents a `BlockEncoding` that is controlled by a clock register.</span></span>

<span data-ttu-id="7c0d1-106">Diğer bir deyişle, bir `TimeDependentBlockEncoding` durum $ \ket{k} _D $ 'ın, `d` Sistem kaydı üzerinde davranan $H _K $, `s` yardımcı durum $ \demet _a $ ' e karşılık gelen sol üst blokta kodlandığı bir $U {0} .</span><span class="sxs-lookup"><span data-stu-id="7c0d1-106">That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="7c0d1-107">Yani</span><span class="sxs-lookup"><span data-stu-id="7c0d1-107">That is,</span></span>

<span data-ttu-id="7c0d1-108">$ $ \begin{hizalaması} (\bra {0} \_ a\otimes I_ {DS}) U (\ayraç {0} \_ a\otimes I_ {DS}) = \ sum_ {k} \ket{k}\bra{k} \_ d\otimes H_k.</span><span class="sxs-lookup"><span data-stu-id="7c0d1-108">$$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k.</span></span>
<span data-ttu-id="7c0d1-109">\end{hizalaması} $ $.</span><span class="sxs-lookup"><span data-stu-id="7c0d1-109">\end{align} $$.</span></span>

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

