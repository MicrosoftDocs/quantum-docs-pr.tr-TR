---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: Rectangulararrayolgu işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730050"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="3c6a0-102">Rectangulararrayolgu işlevi</span><span class="sxs-lookup"><span data-stu-id="3c6a0-102">RectangularArrayFact function</span></span>

<span data-ttu-id="3c6a0-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3c6a0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3c6a0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c6a0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c6a0-105">2 boyutlu dizinin dikdörtgen şekline sahip olduğu koşulu temsil eder</span><span class="sxs-lookup"><span data-stu-id="3c6a0-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="3c6a0-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3c6a0-106">Description</span></span>

<span data-ttu-id="3c6a0-107">Bu işlev, bir dizideki her satırın aynı uzunlukta olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="3c6a0-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="3c6a0-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="3c6a0-109">dizi: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="3c6a0-109">array : 'T[][]</span></span>

<span data-ttu-id="3c6a0-110">2 boyutlu bir öğe dizisi</span><span class="sxs-lookup"><span data-stu-id="3c6a0-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="3c6a0-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="3c6a0-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="3c6a0-112">Dizi dikdörtgen olmayan bir dizi değilse yazdırılacak bir ileti</span><span class="sxs-lookup"><span data-stu-id="3c6a0-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c6a0-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c6a0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3c6a0-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="3c6a0-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3c6a0-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="3c6a0-115">'T</span></span>

<span data-ttu-id="3c6a0-116">Her öğesinin türü `array` .</span><span class="sxs-lookup"><span data-stu-id="3c6a0-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c6a0-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3c6a0-117">See Also</span></span>

- [<span data-ttu-id="3c6a0-118">Microsoft. hisse. Arrays. Squarearrayolgusu</span><span class="sxs-lookup"><span data-stu-id="3c6a0-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)