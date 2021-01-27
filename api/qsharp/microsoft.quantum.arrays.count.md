---
uid: Microsoft.Quantum.Arrays.Count
title: Count işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842844"
---
# <a name="count-function"></a><span data-ttu-id="8e27d-102">Count işlevi</span><span class="sxs-lookup"><span data-stu-id="8e27d-102">Count function</span></span>

<span data-ttu-id="8e27d-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8e27d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8e27d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8e27d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8e27d-105">Dizi öğeleri için tanımlanan bir dizi ve koşul verildiğinde, koşulu karşılayan öğelerden oluşan bir dizi öğe sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="8e27d-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="8e27d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8e27d-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="8e27d-107">koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8e27d-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8e27d-108">`'T`Öğeleri filtrelemek için kullanılan Boolean ile bir işlev.</span><span class="sxs-lookup"><span data-stu-id="8e27d-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="8e27d-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="8e27d-109">array : 'T[]</span></span>

<span data-ttu-id="8e27d-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="8e27d-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="8e27d-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8e27d-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8e27d-112">`array`Koşulunu karşılayan öğe sayısı.</span><span class="sxs-lookup"><span data-stu-id="8e27d-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8e27d-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="8e27d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8e27d-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="8e27d-114">'T</span></span>

<span data-ttu-id="8e27d-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="8e27d-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="8e27d-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="8e27d-116">Example</span></span>

<span data-ttu-id="8e27d-117">Aşağıdaki kod "Count" işlevini gösterir.</span><span class="sxs-lookup"><span data-stu-id="8e27d-117">The following code demonstrates the "Count" function.</span></span>
<span data-ttu-id="8e27d-118">İşlevi kullanılarak bir koşul tanımlanmıştır @"microsoft.quantum.logical.greaterthani" :</span><span class="sxs-lookup"><span data-stu-id="8e27d-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a><span data-ttu-id="8e27d-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8e27d-119">Remarks</span></span>

<span data-ttu-id="8e27d-120">İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve `'T -> Bool` öğeleri filtreleyebilmemiz için bir koşul.</span><span class="sxs-lookup"><span data-stu-id="8e27d-120">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>