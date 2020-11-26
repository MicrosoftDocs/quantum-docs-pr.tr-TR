---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: b1d73c2503e63ed09a3d6a56421760ca29eb0c3f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220697"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="36d2d-102">MappedOverRange işlevi</span><span class="sxs-lookup"><span data-stu-id="36d2d-102">MappedOverRange function</span></span>

<span data-ttu-id="36d2d-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="36d2d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="36d2d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="36d2d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="36d2d-105">Bir Aralık ve girdi olarak tamsayı alan bir işlev verildiğinde, işlev altındaki Aralık değerlerinin görüntülerinden oluşan yeni bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="36d2d-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="36d2d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="36d2d-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="36d2d-107">Eşleyici: [Int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="36d2d-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="36d2d-108">`Int`Aralık değerlerini eşlemek için ' den ' a bir işlev `'T` kullanılır.</span><span class="sxs-lookup"><span data-stu-id="36d2d-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="36d2d-109">Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="36d2d-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="36d2d-110">Bir dizi tamsayı.</span><span class="sxs-lookup"><span data-stu-id="36d2d-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="36d2d-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="36d2d-111">Output : 'T[]</span></span>

<span data-ttu-id="36d2d-112">`'T[]`İşlev tarafından eşlenen öğelerin dizisi `mapper` .</span><span class="sxs-lookup"><span data-stu-id="36d2d-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="36d2d-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="36d2d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="36d2d-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="36d2d-114">'T</span></span>

<span data-ttu-id="36d2d-115">İşlevin sonuç türü `mapper` .</span><span class="sxs-lookup"><span data-stu-id="36d2d-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="36d2d-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="36d2d-116">Remarks</span></span>

<span data-ttu-id="36d2d-117">İşlevi genel türler için tanımlanmıştır, yani, bir işlevimiz olduğunda `mapper: Int -> 'T` aralığın değerlerini eşleyebilir ve türünde bir dizi üretebilir `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="36d2d-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="36d2d-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="36d2d-118">See Also</span></span>

- [<span data-ttu-id="36d2d-119">Microsoft. hisse. Arrays. eşlenmiş</span><span class="sxs-lookup"><span data-stu-id="36d2d-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)