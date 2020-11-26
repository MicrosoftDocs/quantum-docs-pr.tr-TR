---
uid: Microsoft.Quantum.Arrays.Mapped
title: Eşlenen işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 9632b9f53ffad8ece958ab1dc9ad446c7dcb9e13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220748"
---
# <a name="mapped-function"></a><span data-ttu-id="85add-102">Eşlenen işlev</span><span class="sxs-lookup"><span data-stu-id="85add-102">Mapped function</span></span>

<span data-ttu-id="85add-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="85add-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="85add-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85add-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85add-105">Dizi öğeleri için tanımlanan bir dizi ve bir işlev verildiğinde, işlevin altındaki orijinal dizinin görüntülerinden oluşan yeni bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="85add-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="85add-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="85add-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="85add-107">Eşleyici: 'T-> ' U</span><span class="sxs-lookup"><span data-stu-id="85add-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="85add-108">`'T` `'U` Öğeleri eşlemek için kullanılan öğesinden öğesine bir işlev.</span><span class="sxs-lookup"><span data-stu-id="85add-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="85add-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="85add-109">array : 'T[]</span></span>

<span data-ttu-id="85add-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="85add-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="85add-111">Çıkış: ' U []</span><span class="sxs-lookup"><span data-stu-id="85add-111">Output : 'U[]</span></span>

<span data-ttu-id="85add-112">`'U[]`İşlev tarafından eşlenen öğelerin dizisi `mapper` .</span><span class="sxs-lookup"><span data-stu-id="85add-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="85add-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="85add-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="85add-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="85add-114">'T</span></span>

<span data-ttu-id="85add-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="85add-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="85add-116">' U</span><span class="sxs-lookup"><span data-stu-id="85add-116">'U</span></span>

<span data-ttu-id="85add-117">İşlevin sonuç türü `mapper` .</span><span class="sxs-lookup"><span data-stu-id="85add-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="85add-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="85add-118">Remarks</span></span>

<span data-ttu-id="85add-119">İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve bir işlev olduğunda `mapper: 'T -> 'U` dizinin öğelerini eşleyebilir ve yeni türde bir dizi üretebilirsiniz `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="85add-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>