---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: Multiplygeneratorındex işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: b53a483a0c2b8c99b733c9c87289fb212b5ffc89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848027"
---
# <a name="multiplygeneratorindex-function"></a><span data-ttu-id="3a9f2-102">Multiplygeneratorındex işlevi</span><span class="sxs-lookup"><span data-stu-id="3a9f2-102">MultiplyGeneratorIndex function</span></span>

<span data-ttu-id="3a9f2-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3a9f2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3a9f2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3a9f2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3a9f2-105">İçindeki katsayısı çarpar `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="3a9f2-105">Multiplies the coefficient in a `GeneratorIndex`.</span></span>

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="3a9f2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3a9f2-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="3a9f2-107">çarpan: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3a9f2-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3a9f2-108">Katlayıcı üzerindeki çarpan.</span><span class="sxs-lookup"><span data-stu-id="3a9f2-108">The multiplier on the coefficient.</span></span>


### <a name="generatorindex--generatorindex"></a><span data-ttu-id="3a9f2-109">Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3a9f2-109">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3a9f2-110">`GeneratorIndex`Çarpmak için.</span><span class="sxs-lookup"><span data-stu-id="3a9f2-110">The `GeneratorIndex` to be multiplied.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="3a9f2-111">Çıkış: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3a9f2-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3a9f2-112">`GeneratorIndex`Katsayı bir faktörü daha büyük olan bir terimi temsil eder `multiplier` .</span><span class="sxs-lookup"><span data-stu-id="3a9f2-112">A `GeneratorIndex` representing a term with coefficient a factor `multiplier` larger.</span></span>

## <a name="example"></a><span data-ttu-id="3a9f2-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="3a9f2-113">Example</span></span>

```qsharp
let gen = GeneratorIndex(([1,2,3],[coeff]),[1,2,3]);
let ((idxPaulis, idxDoubles), idxQubits) = MultiplyGeneratorIndex(multiplier, gen);
// idxDoubles[0] == multiplier * coeff;
```

## <a name="see-also"></a><span data-ttu-id="3a9f2-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3a9f2-114">See Also</span></span>

- [<span data-ttu-id="3a9f2-115">Microsoft. hisse. simülasyon. Generatorındex</span><span class="sxs-lookup"><span data-stu-id="3a9f2-115">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)