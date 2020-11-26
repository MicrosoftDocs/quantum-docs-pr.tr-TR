---
uid: Microsoft.Quantum.Arrays.Any
title: Any işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: 717ab9ebcbb864a6faf1c14cd36125e589849f2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221666"
---
# <a name="any-function"></a><span data-ttu-id="93bac-102">Any işlevi</span><span class="sxs-lookup"><span data-stu-id="93bac-102">Any function</span></span>

<span data-ttu-id="93bac-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="93bac-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="93bac-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93bac-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93bac-105">Dizi öğeleri için tanımlanan bir dizi ve koşul verildiğinde, dizinin en az bir öğesinin koşulu karşılayıp karşılamadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="93bac-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="93bac-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="93bac-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="93bac-107">koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="93bac-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="93bac-108">`'T` `Bool` Öğeleri denetlemek için kullanılan öğesinden bir işlev.</span><span class="sxs-lookup"><span data-stu-id="93bac-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="93bac-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="93bac-109">array : 'T[]</span></span>

<span data-ttu-id="93bac-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="93bac-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="93bac-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="93bac-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="93bac-112">`Bool`Tüm öğelere uygulanan koşulun OR işlevinin değeri.</span><span class="sxs-lookup"><span data-stu-id="93bac-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="93bac-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="93bac-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93bac-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="93bac-114">'T</span></span>

<span data-ttu-id="93bac-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="93bac-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="93bac-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="93bac-116">Remarks</span></span>

<span data-ttu-id="93bac-117">İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve işlevimiz olduğunda, bir `predicate: 'T -> Bool` `Bool` öğenin karşılayıp karşılamadığını belirten bir değer üretebiliriz `predicate` .</span><span class="sxs-lookup"><span data-stu-id="93bac-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>