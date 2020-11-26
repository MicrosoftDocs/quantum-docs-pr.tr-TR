---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Bölümlenmiş işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220510"
---
# <a name="partitioned-function"></a><span data-ttu-id="48237-102">Bölümlenmiş işlev</span><span class="sxs-lookup"><span data-stu-id="48237-102">Partitioned function</span></span>

<span data-ttu-id="48237-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="48237-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="48237-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48237-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48237-105">Bir diziyi birden çok parçaya böler.</span><span class="sxs-lookup"><span data-stu-id="48237-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="48237-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="48237-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="48237-107">nElements: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="48237-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="48237-108">Dizinin her bir parçasındaki öğe sayısı</span><span class="sxs-lookup"><span data-stu-id="48237-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="48237-109">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="48237-109">arr : 'T[]</span></span>

<span data-ttu-id="48237-110">Bölünecek giriş dizisi.</span><span class="sxs-lookup"><span data-stu-id="48237-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="48237-111">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="48237-111">Output : 'T[][]</span></span>

<span data-ttu-id="48237-112">İlk dizinin birinci ilk `nElements[0]` `arr` ve ikinci dizi ise ve ' nin bir sonraki ' dır `nElements[1]` `arr` . Son dizi kalan tüm öğeleri içerir.</span><span class="sxs-lookup"><span data-stu-id="48237-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="48237-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="48237-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="48237-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="48237-114">'T</span></span>

