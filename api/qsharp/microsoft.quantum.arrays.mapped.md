---
uid: Microsoft.Quantum.Arrays.Mapped
title: Eşlenen işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 00ea0803faf6e8edfa748af63dd6c7e217b1de41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845682"
---
# <a name="mapped-function"></a><span data-ttu-id="ad76e-102">Eşlenen işlev</span><span class="sxs-lookup"><span data-stu-id="ad76e-102">Mapped function</span></span>

<span data-ttu-id="ad76e-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ad76e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ad76e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad76e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad76e-105">Dizi öğeleri için tanımlanan bir dizi ve bir işlev verildiğinde, işlevin altındaki orijinal dizinin görüntülerinden oluşan yeni bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="ad76e-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="ad76e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ad76e-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="ad76e-107">Eşleyici: 'T-> ' U</span><span class="sxs-lookup"><span data-stu-id="ad76e-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="ad76e-108">`'T` `'U` Öğeleri eşlemek için kullanılan öğesinden öğesine bir işlev.</span><span class="sxs-lookup"><span data-stu-id="ad76e-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="ad76e-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="ad76e-109">array : 'T[]</span></span>

<span data-ttu-id="ad76e-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="ad76e-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="ad76e-111">Çıkış: ' U []</span><span class="sxs-lookup"><span data-stu-id="ad76e-111">Output : 'U[]</span></span>

<span data-ttu-id="ad76e-112">`'U[]`İşlev tarafından eşlenen öğelerin dizisi `mapper` .</span><span class="sxs-lookup"><span data-stu-id="ad76e-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ad76e-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ad76e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ad76e-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ad76e-114">'T</span></span>

<span data-ttu-id="ad76e-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="ad76e-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="ad76e-116">' U</span><span class="sxs-lookup"><span data-stu-id="ad76e-116">'U</span></span>

<span data-ttu-id="ad76e-117">İşlevin sonuç türü `mapper` .</span><span class="sxs-lookup"><span data-stu-id="ad76e-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad76e-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ad76e-118">Remarks</span></span>

<span data-ttu-id="ad76e-119">İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve bir işlev olduğunda `mapper: 'T -> 'U` dizinin öğelerini eşleyebilir ve yeni türde bir dizi üretebilirsiniz `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="ad76e-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>