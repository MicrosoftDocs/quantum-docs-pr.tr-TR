---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: Paulicoverimlilik Entfromgenidx işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 59ddadabb5c77cdb0d2e3620a09433992e85f663
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225066"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="9272d-102">Paulicoverimlilik Entfromgenidx işlevi</span><span class="sxs-lookup"><span data-stu-id="9272d-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="9272d-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9272d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9272d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9272d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9272d-105">Tarafından tanımlanan bir Pauli teriminin katsayısını ayıklar `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="9272d-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="9272d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9272d-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="9272d-107">Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9272d-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="9272d-108">`GeneratorIndex` Pauli terimini kodlayan tür.</span><span class="sxs-lookup"><span data-stu-id="9272d-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="9272d-109">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9272d-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9272d-110">Tarafından tanımlanan terimin katsayısı `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="9272d-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>