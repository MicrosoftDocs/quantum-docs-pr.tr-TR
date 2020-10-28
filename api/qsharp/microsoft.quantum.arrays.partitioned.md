---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Bölümlenmiş işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730087"
---
# <a name="partitioned-function"></a><span data-ttu-id="39a07-102">Bölümlenmiş işlev</span><span class="sxs-lookup"><span data-stu-id="39a07-102">Partitioned function</span></span>

<span data-ttu-id="39a07-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="39a07-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="39a07-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39a07-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39a07-105">Bir diziyi birden çok parçaya böler.</span><span class="sxs-lookup"><span data-stu-id="39a07-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="39a07-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="39a07-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="39a07-107">nElements: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="39a07-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="39a07-108">Dizinin her bir parçasındaki öğe sayısı</span><span class="sxs-lookup"><span data-stu-id="39a07-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="39a07-109">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="39a07-109">arr : 'T[]</span></span>

<span data-ttu-id="39a07-110">Bölünecek giriş dizisi.</span><span class="sxs-lookup"><span data-stu-id="39a07-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="39a07-111">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="39a07-111">Output : 'T[][]</span></span>

<span data-ttu-id="39a07-112">İlk dizinin birinci ilk `nElements[0]` `arr` ve ikinci dizi ise ve ' nin bir sonraki ' dır `nElements[1]` `arr` . Son dizi kalan tüm öğeleri içerir.</span><span class="sxs-lookup"><span data-stu-id="39a07-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="39a07-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="39a07-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39a07-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="39a07-114">'T</span></span>

