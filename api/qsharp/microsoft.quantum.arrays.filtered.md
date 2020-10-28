---
uid: Microsoft.Quantum.Arrays.Filtered
title: Filtrelenmiş işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 4c786c69b0896b517f108611e32501867838aeb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730282"
---
# <a name="filtered-function"></a><span data-ttu-id="5d7b8-102">Filtrelenmiş işlev</span><span class="sxs-lookup"><span data-stu-id="5d7b8-102">Filtered function</span></span>

<span data-ttu-id="5d7b8-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5d7b8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5d7b8-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d7b8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5d7b8-105">Dizi öğeleri için tanımlanan bir dizi ve koşul verildiğinde, koşulu karşılayan öğelerden oluşan bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="5d7b8-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="5d7b8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5d7b8-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="5d7b8-107">koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5d7b8-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5d7b8-108">`'T`Öğeleri filtrelemek için kullanılan Boolean ile bir işlev.</span><span class="sxs-lookup"><span data-stu-id="5d7b8-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="5d7b8-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="5d7b8-109">array : 'T[]</span></span>

<span data-ttu-id="5d7b8-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="5d7b8-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="5d7b8-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="5d7b8-111">Output : 'T[]</span></span>

<span data-ttu-id="5d7b8-112">`'T[]`Koşulu karşılayan bir öğe dizisi.</span><span class="sxs-lookup"><span data-stu-id="5d7b8-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5d7b8-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="5d7b8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5d7b8-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="5d7b8-114">'T</span></span>

<span data-ttu-id="5d7b8-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="5d7b8-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d7b8-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5d7b8-116">Remarks</span></span>

<span data-ttu-id="5d7b8-117">İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve `'T -> Bool` öğeleri filtreleyebilmemiz için bir koşul.</span><span class="sxs-lookup"><span data-stu-id="5d7b8-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>