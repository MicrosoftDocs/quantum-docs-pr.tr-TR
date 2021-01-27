---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Bölümlenmiş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845552"
---
# <a name="partitioned-function"></a><span data-ttu-id="f001f-102">Bölümlenmiş işlev</span><span class="sxs-lookup"><span data-stu-id="f001f-102">Partitioned function</span></span>

<span data-ttu-id="f001f-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f001f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f001f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f001f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f001f-105">Bir diziyi birden çok parçaya böler.</span><span class="sxs-lookup"><span data-stu-id="f001f-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="f001f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f001f-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="f001f-107">nElements: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f001f-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f001f-108">Dizinin her bir parçasındaki öğe sayısı</span><span class="sxs-lookup"><span data-stu-id="f001f-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="f001f-109">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="f001f-109">arr : 'T[]</span></span>

<span data-ttu-id="f001f-110">Bölünecek giriş dizisi.</span><span class="sxs-lookup"><span data-stu-id="f001f-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="f001f-111">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="f001f-111">Output : 'T[][]</span></span>

<span data-ttu-id="f001f-112">İlk dizinin birinci ilk `nElements[0]` `arr` ve ikinci dizi ise ve ' nin bir sonraki ' dır `nElements[1]` `arr` . Son dizi kalan tüm öğeleri içerir.</span><span class="sxs-lookup"><span data-stu-id="f001f-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f001f-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f001f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f001f-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f001f-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="f001f-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="f001f-115">Example</span></span>

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```