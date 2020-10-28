---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730130"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="cc3ab-102">MappedOverRange işlevi</span><span class="sxs-lookup"><span data-stu-id="cc3ab-102">MappedOverRange function</span></span>

<span data-ttu-id="cc3ab-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cc3ab-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cc3ab-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc3ab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc3ab-105">Bir Aralık ve girdi olarak tamsayı alan bir işlev verildiğinde, işlev altındaki Aralık değerlerinin görüntülerinden oluşan yeni bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="cc3ab-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="cc3ab-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="cc3ab-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="cc3ab-107">Eşleyici: [Int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="cc3ab-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="cc3ab-108">`Int`Aralık değerlerini eşlemek için ' den ' a bir işlev `'T` kullanılır.</span><span class="sxs-lookup"><span data-stu-id="cc3ab-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="cc3ab-109">Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="cc3ab-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="cc3ab-110">Bir dizi tamsayı.</span><span class="sxs-lookup"><span data-stu-id="cc3ab-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="cc3ab-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="cc3ab-111">Output : 'T[]</span></span>

<span data-ttu-id="cc3ab-112">`'T[]`İşlev tarafından eşlenen öğelerin dizisi `mapper` .</span><span class="sxs-lookup"><span data-stu-id="cc3ab-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cc3ab-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="cc3ab-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cc3ab-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="cc3ab-114">'T</span></span>

<span data-ttu-id="cc3ab-115">İşlevin sonuç türü `mapper` .</span><span class="sxs-lookup"><span data-stu-id="cc3ab-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc3ab-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cc3ab-116">Remarks</span></span>

<span data-ttu-id="cc3ab-117">İşlevi genel türler için tanımlanmıştır, yani, bir işlevimiz olduğunda `mapper: Int -> 'T` aralığın değerlerini eşleyebilir ve türünde bir dizi üretebilir `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="cc3ab-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc3ab-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="cc3ab-118">See Also</span></span>

- [<span data-ttu-id="cc3ab-119">Microsoft. hisse. Arrays. eşlenmiş</span><span class="sxs-lookup"><span data-stu-id="cc3ab-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)