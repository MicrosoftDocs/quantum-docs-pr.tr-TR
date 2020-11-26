---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: Rectangulararrayolgu işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220425"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="186a2-102">Rectangulararrayolgu işlevi</span><span class="sxs-lookup"><span data-stu-id="186a2-102">RectangularArrayFact function</span></span>

<span data-ttu-id="186a2-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="186a2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="186a2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="186a2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="186a2-105">2 boyutlu dizinin dikdörtgen şekline sahip olduğu koşulu temsil eder</span><span class="sxs-lookup"><span data-stu-id="186a2-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="186a2-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="186a2-106">Description</span></span>

<span data-ttu-id="186a2-107">Bu işlev, bir dizideki her satırın aynı uzunlukta olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="186a2-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="186a2-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="186a2-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="186a2-109">dizi: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="186a2-109">array : 'T[][]</span></span>

<span data-ttu-id="186a2-110">2 boyutlu bir öğe dizisi</span><span class="sxs-lookup"><span data-stu-id="186a2-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="186a2-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="186a2-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="186a2-112">Dizi dikdörtgen olmayan bir dizi değilse yazdırılacak bir ileti</span><span class="sxs-lookup"><span data-stu-id="186a2-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="186a2-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="186a2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="186a2-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="186a2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="186a2-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="186a2-115">'T</span></span>

<span data-ttu-id="186a2-116">Her öğesinin türü `array` .</span><span class="sxs-lookup"><span data-stu-id="186a2-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="186a2-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="186a2-117">See Also</span></span>

- [<span data-ttu-id="186a2-118">Microsoft. hisse. Arrays. Squarearrayolgusu</span><span class="sxs-lookup"><span data-stu-id="186a2-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)