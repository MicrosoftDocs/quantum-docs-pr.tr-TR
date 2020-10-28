---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: Timedependentblockenkodlamaya göre Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: 1cb3a3cf1e16b194eebd1574da6f9934fc34e5f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734223"
---
# <a name="timedependentblockencoding-user-defined-type"></a><span data-ttu-id="4b98b-102">Timedependentblockenkodlamaya göre Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="4b98b-102">TimeDependentBlockEncoding user defined type</span></span>

<span data-ttu-id="4b98b-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4b98b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4b98b-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b98b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b98b-105">Bir `BlockEncoding` saat kaydı tarafından denetlenen bir öğesini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="4b98b-105">Represents a `BlockEncoding` that is controlled by a clock register.</span></span>

<span data-ttu-id="4b98b-106">Diğer bir deyişle, bir `TimeDependentBlockEncoding` durum $ \ket{k} _D $ 'ın, `d` Sistem kaydı üzerinde davranan $H _K $, `s` yardımcı durum $ \demet _a $ ' e karşılık gelen sol üst blokta kodlandığı bir $U {0} .</span><span class="sxs-lookup"><span data-stu-id="4b98b-106">That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="4b98b-107">Yani</span><span class="sxs-lookup"><span data-stu-id="4b98b-107">That is,</span></span>

<span data-ttu-id="4b98b-108">$ $ \begin{hizalaması} (\bra {0} \_ a\otimes I_ {DS}) U (\ayraç {0} \_ a\otimes I_ {DS}) = \ sum_ {k} \ket{k}\bra{k} \_ d\otimes H_k.</span><span class="sxs-lookup"><span data-stu-id="4b98b-108">$$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k.</span></span>
<span data-ttu-id="4b98b-109">\end{hizalaması} $ $.</span><span class="sxs-lookup"><span data-stu-id="4b98b-109">\end{align} $$.</span></span>

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

