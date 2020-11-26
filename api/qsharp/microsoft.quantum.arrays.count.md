---
uid: Microsoft.Quantum.Arrays.Count
title: Count işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 48b75cc6d6584f899223a0803f31fd174836f303
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221564"
---
# <a name="count-function"></a><span data-ttu-id="c7da3-102">Count işlevi</span><span class="sxs-lookup"><span data-stu-id="c7da3-102">Count function</span></span>

<span data-ttu-id="c7da3-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c7da3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c7da3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c7da3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c7da3-105">Dizi öğeleri için tanımlanan bir dizi ve koşul verildiğinde, koşulu karşılayan öğelerden oluşan bir dizi öğe sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="c7da3-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="c7da3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c7da3-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="c7da3-107">koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c7da3-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c7da3-108">`'T`Öğeleri filtrelemek için kullanılan Boolean ile bir işlev.</span><span class="sxs-lookup"><span data-stu-id="c7da3-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="c7da3-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="c7da3-109">array : 'T[]</span></span>

<span data-ttu-id="c7da3-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="c7da3-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="c7da3-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c7da3-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c7da3-112">`array`Koşulunu karşılayan öğe sayısı.</span><span class="sxs-lookup"><span data-stu-id="c7da3-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c7da3-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c7da3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c7da3-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c7da3-114">'T</span></span>

<span data-ttu-id="c7da3-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="c7da3-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7da3-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c7da3-116">Remarks</span></span>

<span data-ttu-id="c7da3-117">İşlevi genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve `'T -> Bool` öğeleri filtreleyebilmemiz için bir koşul.</span><span class="sxs-lookup"><span data-stu-id="c7da3-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>