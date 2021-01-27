---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858420"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="d35f0-102">GeneratorSystem Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="d35f0-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="d35f0-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d35f0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d35f0-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d35f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d35f0-105">Bir es koleksiyonunu temsil eder `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="d35f0-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="d35f0-106">Tek Dizin tamsayı kullanarak bu koleksiyonu yineliyoruz ve koleksiyonun boyutunun bilindiği varsayılır.</span><span class="sxs-lookup"><span data-stu-id="d35f0-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="d35f0-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d35f0-107">Remarks</span></span>

<span data-ttu-id="d35f0-108">Örnekleri `GeneratorSystem` , işlevi kullanılarak kolayca tanımlanabilir <xref:microsoft.quantum.arrays.lookupfunction> .</span><span class="sxs-lookup"><span data-stu-id="d35f0-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="d35f0-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d35f0-109">See Also</span></span>

- [<span data-ttu-id="d35f0-110">Microsoft. hisse. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="d35f0-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)