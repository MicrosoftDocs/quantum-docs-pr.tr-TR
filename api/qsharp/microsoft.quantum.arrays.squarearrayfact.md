---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: Squarearrayolgu işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: f7f0573db9098feebfd481624e11119c58fd9eed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730007"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="4ef04-102">Squarearrayolgu işlevi</span><span class="sxs-lookup"><span data-stu-id="4ef04-102">SquareArrayFact function</span></span>

<span data-ttu-id="4ef04-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4ef04-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4ef04-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4ef04-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4ef04-105">2 boyutlu dizinin kare şekline sahip olduğu koşulu temsil eder</span><span class="sxs-lookup"><span data-stu-id="4ef04-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="4ef04-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4ef04-106">Description</span></span>

<span data-ttu-id="4ef04-107">Bu işlev, dizideki her bir satırın dizideki satırlar (öğeler) gibi çok sayıda öğesi olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="4ef04-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="4ef04-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="4ef04-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="4ef04-109">dizi: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="4ef04-109">array : 'T[][]</span></span>

<span data-ttu-id="4ef04-110">2 boyutlu bir öğe dizisi</span><span class="sxs-lookup"><span data-stu-id="4ef04-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="4ef04-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4ef04-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4ef04-112">Dizi bir kare dizisi değilse yazdırılacak bir ileti</span><span class="sxs-lookup"><span data-stu-id="4ef04-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="4ef04-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4ef04-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4ef04-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="4ef04-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4ef04-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="4ef04-115">'T</span></span>

<span data-ttu-id="4ef04-116">Her öğesinin türü `array` .</span><span class="sxs-lookup"><span data-stu-id="4ef04-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ef04-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4ef04-117">See Also</span></span>

- [<span data-ttu-id="4ef04-118">Microsoft. hisse. Arrays. Rectangulararrayolgusu</span><span class="sxs-lookup"><span data-stu-id="4ef04-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)