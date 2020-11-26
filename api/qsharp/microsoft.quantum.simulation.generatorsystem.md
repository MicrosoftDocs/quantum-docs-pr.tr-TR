---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225236"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="1f36b-102">GeneratorSystem Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="1f36b-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="1f36b-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1f36b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1f36b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f36b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f36b-105">Bir es koleksiyonunu temsil eder `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="1f36b-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="1f36b-106">Tek Dizin tamsayı kullanarak bu koleksiyonu yineliyoruz ve koleksiyonun boyutunun bilindiği varsayılır.</span><span class="sxs-lookup"><span data-stu-id="1f36b-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="1f36b-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1f36b-107">Remarks</span></span>

<span data-ttu-id="1f36b-108">Örnekleri `GeneratorSystem` , işlevi kullanılarak kolayca tanımlanabilir <xref:microsoft.quantum.arrays.lookupfunction> .</span><span class="sxs-lookup"><span data-stu-id="1f36b-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f36b-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1f36b-109">See Also</span></span>

- [<span data-ttu-id="1f36b-110">Microsoft. hisse. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="1f36b-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)