---
uid: Microsoft.Quantum.Arrays.EqualA
title: EqualA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730295"
---
# <a name="equala-function"></a><span data-ttu-id="cb185-102">EqualA işlevi</span><span class="sxs-lookup"><span data-stu-id="cb185-102">EqualA function</span></span>

<span data-ttu-id="cb185-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cb185-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cb185-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb185-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb185-105">Aynı türde iki dizi ve dizilerin öğe çiftleri için tanımlanan bir koşul verildiğinde, dizilerin eşit olup olmadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="cb185-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="cb185-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="cb185-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="cb185-107">eşittir: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cb185-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cb185-108">`('T, 'T)` `Bool` Dizi içindeki iki öğenin eşit olup olmadığını denetlemek için kullanılan, kayıt kümesinden bir işlev.</span><span class="sxs-lookup"><span data-stu-id="cb185-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="cb185-109">Dizi1: 'T []</span><span class="sxs-lookup"><span data-stu-id="cb185-109">array1 : 'T[]</span></span>

<span data-ttu-id="cb185-110">Karşılaştırılacak ilk dizi.</span><span class="sxs-lookup"><span data-stu-id="cb185-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="cb185-111">dizi2: 'T []</span><span class="sxs-lookup"><span data-stu-id="cb185-111">array2 : 'T[]</span></span>

<span data-ttu-id="cb185-112">Karşılaştırılacak ikinci dizi.</span><span class="sxs-lookup"><span data-stu-id="cb185-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cb185-113">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cb185-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cb185-114">Yalnızca ve `true` `array1` `array2` eşitse değeri.</span><span class="sxs-lookup"><span data-stu-id="cb185-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="cb185-115">Diğer bir deyişle, her iki dizi de aynı uzunluktadır ve tüm öğeler tarafından tanımlanan şekilde eşittir `equal` .</span><span class="sxs-lookup"><span data-stu-id="cb185-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cb185-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="cb185-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cb185-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="cb185-117">'T</span></span>

<span data-ttu-id="cb185-118">Her bir dizinin öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="cb185-118">The type of each array's elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb185-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cb185-119">Remarks</span></span>

<span data-ttu-id="cb185-120">Bu işlev genel türler için tanımlanmıştır; Yani, iki dizimiz `'T[]` ve bir işlev olduğunda `equal: ('T, 'T) -> Bool` , bu işlev `Bool` dizilerinin eşit olup olmadığını gösteren bir değer döndürür.</span><span class="sxs-lookup"><span data-stu-id="cb185-120">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="cb185-121">Eşit kabul edilmesi için iki dizinin eşit olması gerekir ve dizilerdeki aynı konumlarda bulunan öğelerin eşit olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="cb185-121">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>