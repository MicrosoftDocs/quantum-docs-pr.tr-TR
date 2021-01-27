---
uid: Microsoft.Quantum.Arrays.EqualA
title: EqualA işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848684"
---
# <a name="equala-function"></a><span data-ttu-id="2d040-102">EqualA işlevi</span><span class="sxs-lookup"><span data-stu-id="2d040-102">EqualA function</span></span>

<span data-ttu-id="2d040-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2d040-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2d040-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d040-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d040-105">Aynı türde iki dizi ve dizilerin öğe çiftleri için tanımlanan bir koşul verildiğinde, dizilerin eşit olup olmadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="2d040-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="2d040-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2d040-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="2d040-107">eşittir: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2d040-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2d040-108">`('T, 'T)` `Bool` Dizi içindeki iki öğenin eşit olup olmadığını denetlemek için kullanılan, kayıt kümesinden bir işlev.</span><span class="sxs-lookup"><span data-stu-id="2d040-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="2d040-109">Dizi1: 'T []</span><span class="sxs-lookup"><span data-stu-id="2d040-109">array1 : 'T[]</span></span>

<span data-ttu-id="2d040-110">Karşılaştırılacak ilk dizi.</span><span class="sxs-lookup"><span data-stu-id="2d040-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="2d040-111">dizi2: 'T []</span><span class="sxs-lookup"><span data-stu-id="2d040-111">array2 : 'T[]</span></span>

<span data-ttu-id="2d040-112">Karşılaştırılacak ikinci dizi.</span><span class="sxs-lookup"><span data-stu-id="2d040-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2d040-113">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2d040-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2d040-114">Yalnızca ve `true` `array1` `array2` eşitse değeri.</span><span class="sxs-lookup"><span data-stu-id="2d040-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="2d040-115">Diğer bir deyişle, her iki dizi de aynı uzunluktadır ve tüm öğeler tarafından tanımlanan şekilde eşittir `equal` .</span><span class="sxs-lookup"><span data-stu-id="2d040-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2d040-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2d040-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2d040-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="2d040-117">'T</span></span>

<span data-ttu-id="2d040-118">Her bir dizinin öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="2d040-118">The type of each array's elements.</span></span>

## <a name="example"></a><span data-ttu-id="2d040-119">Örnek</span><span class="sxs-lookup"><span data-stu-id="2d040-119">Example</span></span>

<span data-ttu-id="2d040-120">Aşağıdaki kod, farklı dizi çiftlerinin eşit olup olmadığını denetler:</span><span class="sxs-lookup"><span data-stu-id="2d040-120">The following code checks whether different pairs of arrays are equal:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a><span data-ttu-id="2d040-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2d040-121">Remarks</span></span>

<span data-ttu-id="2d040-122">Bu işlev genel türler için tanımlanmıştır; Yani, iki dizimiz `'T[]` ve bir işlev olduğunda `equal: ('T, 'T) -> Bool` , bu işlev `Bool` dizilerinin eşit olup olmadığını gösteren bir değer döndürür.</span><span class="sxs-lookup"><span data-stu-id="2d040-122">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="2d040-123">Eşit kabul edilmesi için iki dizinin eşit olması gerekir ve dizilerdeki aynı konumlarda bulunan öğelerin eşit olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="2d040-123">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>