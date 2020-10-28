---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: Paulicoverimlilik Entfromgenidx işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 5bbc8d6113fb36bfd4050b98538bb61bbac02185
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730911"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="3dd6e-102">Paulicoverimlilik Entfromgenidx işlevi</span><span class="sxs-lookup"><span data-stu-id="3dd6e-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="3dd6e-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3dd6e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3dd6e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3dd6e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3dd6e-105">Tarafından tanımlanan bir Pauli teriminin katsayısını ayıklar `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="3dd6e-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="3dd6e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3dd6e-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="3dd6e-107">Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3dd6e-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3dd6e-108">`GeneratorIndex` Pauli terimini kodlayan tür.</span><span class="sxs-lookup"><span data-stu-id="3dd6e-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="3dd6e-109">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3dd6e-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3dd6e-110">Tarafından tanımlanan terimin katsayısı `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="3dd6e-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>