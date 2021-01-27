---
uid: Microsoft.Quantum.Arrays.Filtered
title: Filtrelenmiş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847155"
---
# <a name="filtered-function"></a><span data-ttu-id="daa7f-102">Filtrelenmiş işlev</span><span class="sxs-lookup"><span data-stu-id="daa7f-102">Filtered function</span></span>

<span data-ttu-id="daa7f-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="daa7f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="daa7f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="daa7f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="daa7f-105">Dizi öğeleri için tanımlanan bir dizi ve koşul verildiğinde, koşulu karşılayan öğelerden oluşan bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="daa7f-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="daa7f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="daa7f-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="daa7f-107">koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="daa7f-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="daa7f-108">`'T`Öğeleri filtrelemek için kullanılan Boolean ile bir işlev.</span><span class="sxs-lookup"><span data-stu-id="daa7f-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="daa7f-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="daa7f-109">array : 'T[]</span></span>

<span data-ttu-id="daa7f-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="daa7f-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="daa7f-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="daa7f-111">Output : 'T[]</span></span>

<span data-ttu-id="daa7f-112">`'T[]`Koşulu karşılayan bir öğe dizisi.</span><span class="sxs-lookup"><span data-stu-id="daa7f-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="daa7f-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="daa7f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="daa7f-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="daa7f-114">'T</span></span>

<span data-ttu-id="daa7f-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="daa7f-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="daa7f-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="daa7f-116">Example</span></span>

<span data-ttu-id="daa7f-117">Aşağıdaki kod "filtrelenmiş" işlevini gösterir.</span><span class="sxs-lookup"><span data-stu-id="daa7f-117">The following code demonstrates the "Filtered" function.</span></span>
<span data-ttu-id="daa7f-118">İşlevi kullanılarak bir koşul tanımlanmıştır @"microsoft.quantum.logical.greaterthani" :</span><span class="sxs-lookup"><span data-stu-id="daa7f-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

<span data-ttu-id="daa7f-119">Bu örnekte beklenen sonuç, 5 ' ten büyük bir sayı dizisi olacak.</span><span class="sxs-lookup"><span data-stu-id="daa7f-119">The outcome one should expect from this example will be an array of numbers greater than 5.</span></span>

## <a name="remarks"></a><span data-ttu-id="daa7f-120">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="daa7f-120">Remarks</span></span>

<span data-ttu-id="daa7f-121">İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve `'T -> Bool` öğeleri filtreleyebilmemiz için bir koşul.</span><span class="sxs-lookup"><span data-stu-id="daa7f-121">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>