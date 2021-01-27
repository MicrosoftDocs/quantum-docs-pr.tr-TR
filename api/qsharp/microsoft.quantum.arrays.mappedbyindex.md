---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: Mappedbyındex işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845658"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="cea9c-102">Mappedbyındex işlevi</span><span class="sxs-lookup"><span data-stu-id="cea9c-102">MappedByIndex function</span></span>

<span data-ttu-id="cea9c-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cea9c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cea9c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cea9c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cea9c-105">Bir dizi ve dizinin dizinli öğeleri için tanımlanan bir işlev verildiğinde, işlevin altındaki orijinal dizinin görüntülerinden oluşan yeni bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="cea9c-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="cea9c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="cea9c-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="cea9c-107">Eşleyici: ([Int](xref:microsoft.quantum.lang-ref.int), 't)-> ' U</span><span class="sxs-lookup"><span data-stu-id="cea9c-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="cea9c-108">`(Int, 'T)` `'U` Öğesi ve bunların dizinlerini eşlemek için kullanılan öğesinden bir işlevi.</span><span class="sxs-lookup"><span data-stu-id="cea9c-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="cea9c-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="cea9c-109">array : 'T[]</span></span>

<span data-ttu-id="cea9c-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="cea9c-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="cea9c-111">Çıkış: ' U []</span><span class="sxs-lookup"><span data-stu-id="cea9c-111">Output : 'U[]</span></span>

<span data-ttu-id="cea9c-112">`'U[]`İşlev tarafından eşlenen öğelerin dizisi `mapper` .</span><span class="sxs-lookup"><span data-stu-id="cea9c-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cea9c-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="cea9c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cea9c-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="cea9c-114">'T</span></span>

<span data-ttu-id="cea9c-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="cea9c-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="cea9c-116">' U</span><span class="sxs-lookup"><span data-stu-id="cea9c-116">'U</span></span>

<span data-ttu-id="cea9c-117">İşlevin sonuç türü `mapper` .</span><span class="sxs-lookup"><span data-stu-id="cea9c-117">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="cea9c-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="cea9c-118">Example</span></span>

<span data-ttu-id="cea9c-119">Aşağıdaki iki satır eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="cea9c-119">The following two lines are equivalent:</span></span>

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

<span data-ttu-id="cea9c-120">ve</span><span class="sxs-lookup"><span data-stu-id="cea9c-120">and</span></span>

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a><span data-ttu-id="cea9c-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="cea9c-121">See Also</span></span>

- [<span data-ttu-id="cea9c-122">Microsoft. hisse. Arrays. eşlenmiş</span><span class="sxs-lookup"><span data-stu-id="cea9c-122">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)