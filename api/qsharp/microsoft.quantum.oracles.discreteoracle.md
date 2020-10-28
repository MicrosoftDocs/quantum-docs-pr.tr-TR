---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: DiscreteOracle Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: ccbcc92d4b6f1c800b576ad54739d26665e6d6d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733746"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="a9d66-102">DiscreteOracle Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="a9d66-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="a9d66-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="a9d66-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="a9d66-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9d66-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9d66-105">Ayrı bir Oracle 'ı temsil eder.</span><span class="sxs-lookup"><span data-stu-id="a9d66-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="a9d66-106">Bu, bir sabit işlem $U $ ve negatif olmayan bir tamsayı $m $ için $U ^ d $ uygulayan bir Oracle ' dır.</span><span class="sxs-lookup"><span data-stu-id="a9d66-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

