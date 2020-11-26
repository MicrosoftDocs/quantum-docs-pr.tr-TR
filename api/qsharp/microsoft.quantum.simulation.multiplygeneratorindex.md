---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: Multiplygeneratorındex işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: dc2bd02c40b53eca726f70578e3c5918add8f1bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230455"
---
# <a name="multiplygeneratorindex-function"></a><span data-ttu-id="9a7cb-102">Multiplygeneratorındex işlevi</span><span class="sxs-lookup"><span data-stu-id="9a7cb-102">MultiplyGeneratorIndex function</span></span>

<span data-ttu-id="9a7cb-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9a7cb-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9a7cb-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a7cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a7cb-105">İçindeki katsayısı çarpar `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="9a7cb-105">Multiplies the coefficient in a `GeneratorIndex`.</span></span>

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="9a7cb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9a7cb-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="9a7cb-107">çarpan: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9a7cb-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9a7cb-108">Katlayıcı üzerindeki çarpan.</span><span class="sxs-lookup"><span data-stu-id="9a7cb-108">The multiplier on the coefficient.</span></span>


### <a name="generatorindex--generatorindex"></a><span data-ttu-id="9a7cb-109">Generatorındex: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9a7cb-109">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="9a7cb-110">`GeneratorIndex`Çarpmak için.</span><span class="sxs-lookup"><span data-stu-id="9a7cb-110">The `GeneratorIndex` to be multiplied.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="9a7cb-111">Çıkış: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9a7cb-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="9a7cb-112">`GeneratorIndex`Katsayı bir faktörü daha büyük olan bir terimi temsil eder `multiplier` .</span><span class="sxs-lookup"><span data-stu-id="9a7cb-112">A `GeneratorIndex` representing a term with coefficient a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a7cb-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9a7cb-113">See Also</span></span>

- [<span data-ttu-id="9a7cb-114">Microsoft. hisse. simülasyon. Generatorındex</span><span class="sxs-lookup"><span data-stu-id="9a7cb-114">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)