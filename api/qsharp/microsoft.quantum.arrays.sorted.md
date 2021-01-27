---
uid: Microsoft.Quantum.Arrays.Sorted
title: Sıralanmış işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845438"
---
# <a name="sorted-function"></a><span data-ttu-id="87f85-102">Sıralanmış işlev</span><span class="sxs-lookup"><span data-stu-id="87f85-102">Sorted function</span></span>

<span data-ttu-id="87f85-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="87f85-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="87f85-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="87f85-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="87f85-105">Dizi verildiğinde, belirli bir karşılaştırma işlevine göre sıralanan bu dizinin öğelerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="87f85-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="87f85-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="87f85-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="87f85-107">Karşılaştırma: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="87f85-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="87f85-108">İki öğeyi karşılaştıran bir işlev `a` , daha küçük veya eşittir olarak kabul edilir `b` `comparison(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="87f85-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="87f85-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="87f85-109">array : 'T[]</span></span>

<span data-ttu-id="87f85-110">Sıralanacak dizi.</span><span class="sxs-lookup"><span data-stu-id="87f85-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="87f85-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="87f85-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="87f85-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="87f85-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="87f85-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="87f85-113">'T</span></span>

<span data-ttu-id="87f85-114">Her öğesinin türü `array` .</span><span class="sxs-lookup"><span data-stu-id="87f85-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="87f85-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="87f85-115">Example</span></span>

<span data-ttu-id="87f85-116">Aşağıdaki kod parçacığı, bir tamsayılar dizisini artan sırada gerçekleşecek şekilde sıralar:</span><span class="sxs-lookup"><span data-stu-id="87f85-116">The following snippet sorts an array of integers to occur in ascending order:</span></span>

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a><span data-ttu-id="87f85-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="87f85-117">Remarks</span></span>

<span data-ttu-id="87f85-118">İşlevin `comparison` geçişli olduğu varsayılır, `comparison(a, b)` ve `comparison(b, c)` daha sonra `comparison(a, c)` varsayılır.</span><span class="sxs-lookup"><span data-stu-id="87f85-118">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="87f85-119">Bu özellik tutmadıysanız, bu işlevin çıktısı yanlış olabilir.</span><span class="sxs-lookup"><span data-stu-id="87f85-119">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="87f85-120">Bu bir işlev olduğundan, iki öğe içinde eşit kabul edildiğinde bile sonuçlar tamamen belirleyici olur `comparison` ; Yani, `comparison(a, b)` ve `comparison(b, a)` her ikisi de olur `true` .</span><span class="sxs-lookup"><span data-stu-id="87f85-120">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="87f85-121">Özellikle, bu işlev tarafından gerçekleştirilen sıralamanın kararlı olduğu garanti edilir. böylece, iki öğe ve `a` `b` içinde bu sırada gerçekleşirse `array` `comparison` , ve sonrasında `a` da daha önce de görüntülenir `b` .</span><span class="sxs-lookup"><span data-stu-id="87f85-121">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="87f85-122">Örnek:</span><span class="sxs-lookup"><span data-stu-id="87f85-122">For example:</span></span>

```qsharp
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```