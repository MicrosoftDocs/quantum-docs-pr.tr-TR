---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: Rectangulararrayolgu işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: 8cf6b85da6e8fee7fc255a173753a6468d8134b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845495"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="2f367-102">Rectangulararrayolgu işlevi</span><span class="sxs-lookup"><span data-stu-id="2f367-102">RectangularArrayFact function</span></span>

<span data-ttu-id="2f367-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2f367-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2f367-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f367-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f367-105">2 boyutlu dizinin dikdörtgen şekline sahip olduğu koşulu temsil eder</span><span class="sxs-lookup"><span data-stu-id="2f367-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="2f367-106">Description</span><span class="sxs-lookup"><span data-stu-id="2f367-106">Description</span></span>

<span data-ttu-id="2f367-107">Bu işlev, bir dizideki her satırın aynı uzunlukta olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="2f367-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="2f367-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="2f367-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="2f367-109">dizi: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="2f367-109">array : 'T[][]</span></span>

<span data-ttu-id="2f367-110">2 boyutlu bir öğe dizisi</span><span class="sxs-lookup"><span data-stu-id="2f367-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="2f367-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2f367-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2f367-112">Dizi dikdörtgen olmayan bir dizi değilse yazdırılacak bir ileti</span><span class="sxs-lookup"><span data-stu-id="2f367-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f367-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f367-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2f367-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2f367-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2f367-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="2f367-115">'T</span></span>

<span data-ttu-id="2f367-116">Her öğesinin türü `array` .</span><span class="sxs-lookup"><span data-stu-id="2f367-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="2f367-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="2f367-117">Example</span></span>

```qsharp
RectangularArrayFact([[1, 2], [3, 4]], "Array is not rectangular");       // okay
RectangularArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not rectangular"); // okay
RectangularArrayFact([[1, 2], [3, 4, 5]], "Array is not rectangular");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="2f367-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2f367-118">See Also</span></span>

- [<span data-ttu-id="2f367-119">Microsoft. hisse. Arrays. Squarearrayolgusu</span><span class="sxs-lookup"><span data-stu-id="2f367-119">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)