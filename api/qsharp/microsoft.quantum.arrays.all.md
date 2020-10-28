---
uid: Microsoft.Quantum.Arrays.All
title: All işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 345c3fb92babd4ae2e54803b6c3b79b3313ef417
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730423"
---
# <a name="all-function"></a><span data-ttu-id="074bc-102">All işlevi</span><span class="sxs-lookup"><span data-stu-id="074bc-102">All function</span></span>

<span data-ttu-id="074bc-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="074bc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="074bc-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="074bc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="074bc-105">Dizi öğeleri için tanımlanan bir dizi ve koşul verildiğinde, dizideki tüm öğelerin koşulu karşılayıp karşılamadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="074bc-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="074bc-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="074bc-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="074bc-107">koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="074bc-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="074bc-108">`'T` `Bool` Öğeleri denetlemek için kullanılan öğesinden bir işlev.</span><span class="sxs-lookup"><span data-stu-id="074bc-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="074bc-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="074bc-109">array : 'T[]</span></span>

<span data-ttu-id="074bc-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="074bc-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="074bc-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="074bc-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="074bc-112">`Bool`Tüm öğelere uygulanan koşulun ve işlevinin değeri.</span><span class="sxs-lookup"><span data-stu-id="074bc-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="074bc-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="074bc-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="074bc-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="074bc-114">'T</span></span>

<span data-ttu-id="074bc-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="074bc-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="074bc-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="074bc-116">Remarks</span></span>

<span data-ttu-id="074bc-117">İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve bir işlev olduğunda `predicate: 'T -> Bool` `Bool` tüm öğelerin karşılayıp karşılamadığını belirten bir değer üretebiliriz `predicate` .</span><span class="sxs-lookup"><span data-stu-id="074bc-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>