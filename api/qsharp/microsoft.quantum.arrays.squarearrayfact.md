---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: Squarearrayolgu işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: a154e5becba4dae762596a3fc1b268855520fa1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850976"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="bc4cb-102">Squarearrayolgu işlevi</span><span class="sxs-lookup"><span data-stu-id="bc4cb-102">SquareArrayFact function</span></span>

<span data-ttu-id="bc4cb-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bc4cb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bc4cb-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bc4cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bc4cb-105">2 boyutlu dizinin kare şekline sahip olduğu koşulu temsil eder</span><span class="sxs-lookup"><span data-stu-id="bc4cb-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="bc4cb-106">Description</span><span class="sxs-lookup"><span data-stu-id="bc4cb-106">Description</span></span>

<span data-ttu-id="bc4cb-107">Bu işlev, dizideki her bir satırın dizideki satırlar (öğeler) gibi çok sayıda öğesi olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="bc4cb-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="bc4cb-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="bc4cb-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="bc4cb-109">dizi: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="bc4cb-109">array : 'T[][]</span></span>

<span data-ttu-id="bc4cb-110">2 boyutlu bir öğe dizisi</span><span class="sxs-lookup"><span data-stu-id="bc4cb-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="bc4cb-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bc4cb-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="bc4cb-112">Dizi bir kare dizisi değilse yazdırılacak bir ileti</span><span class="sxs-lookup"><span data-stu-id="bc4cb-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="bc4cb-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc4cb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bc4cb-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="bc4cb-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc4cb-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="bc4cb-115">'T</span></span>

<span data-ttu-id="bc4cb-116">Her öğesinin türü `array` .</span><span class="sxs-lookup"><span data-stu-id="bc4cb-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="bc4cb-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="bc4cb-117">Example</span></span>

```qsharp
SquareArrayFact([[1, 2], [3, 4]], "Array is not a square");       // okay
SquareArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not a square"); // will fail
SquareArrayFact([[1, 2], [3, 4, 5]], "Array is not a square");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="bc4cb-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bc4cb-118">See Also</span></span>

- [<span data-ttu-id="bc4cb-119">Microsoft. hisse. Arrays. Rectangulararrayolgusu</span><span class="sxs-lookup"><span data-stu-id="bc4cb-119">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)