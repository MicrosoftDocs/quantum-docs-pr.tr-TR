---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733538"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="7aec2-102">GeneratorSystem Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="7aec2-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="7aec2-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7aec2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7aec2-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7aec2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7aec2-105">Bir es koleksiyonunu temsil eder `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="7aec2-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="7aec2-106">Tek Dizin tamsayı kullanarak bu koleksiyonu yineliyoruz ve koleksiyonun boyutunun bilindiği varsayılır.</span><span class="sxs-lookup"><span data-stu-id="7aec2-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="7aec2-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7aec2-107">Remarks</span></span>

<span data-ttu-id="7aec2-108">Örnekleri `GeneratorSystem` , işlevi kullanılarak kolayca tanımlanabilir <xref:microsoft.quantum.arrays.lookupfunction> .</span><span class="sxs-lookup"><span data-stu-id="7aec2-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="7aec2-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7aec2-109">See Also</span></span>

- [<span data-ttu-id="7aec2-110">Microsoft. hisse. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="7aec2-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)