---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: Mappedbyındex işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730138"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="a65d5-102">Mappedbyındex işlevi</span><span class="sxs-lookup"><span data-stu-id="a65d5-102">MappedByIndex function</span></span>

<span data-ttu-id="a65d5-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a65d5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a65d5-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a65d5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a65d5-105">Bir dizi ve dizinin dizinli öğeleri için tanımlanan bir işlev verildiğinde, işlevin altındaki orijinal dizinin görüntülerinden oluşan yeni bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="a65d5-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="a65d5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a65d5-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="a65d5-107">Eşleyici: ([Int](xref:microsoft.quantum.lang-ref.int), 't)-> ' U</span><span class="sxs-lookup"><span data-stu-id="a65d5-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="a65d5-108">`(Int, 'T)` `'U` Öğesi ve bunların dizinlerini eşlemek için kullanılan öğesinden bir işlevi.</span><span class="sxs-lookup"><span data-stu-id="a65d5-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="a65d5-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="a65d5-109">array : 'T[]</span></span>

<span data-ttu-id="a65d5-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="a65d5-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="a65d5-111">Çıkış: ' U []</span><span class="sxs-lookup"><span data-stu-id="a65d5-111">Output : 'U[]</span></span>

<span data-ttu-id="a65d5-112">`'U[]`İşlev tarafından eşlenen öğelerin dizisi `mapper` .</span><span class="sxs-lookup"><span data-stu-id="a65d5-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a65d5-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="a65d5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a65d5-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="a65d5-114">'T</span></span>

<span data-ttu-id="a65d5-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="a65d5-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="a65d5-116">' U</span><span class="sxs-lookup"><span data-stu-id="a65d5-116">'U</span></span>

<span data-ttu-id="a65d5-117">İşlevin sonuç türü `mapper` .</span><span class="sxs-lookup"><span data-stu-id="a65d5-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="a65d5-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a65d5-118">See Also</span></span>

- [<span data-ttu-id="a65d5-119">Microsoft. hisse. Arrays. eşlenmiş</span><span class="sxs-lookup"><span data-stu-id="a65d5-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)