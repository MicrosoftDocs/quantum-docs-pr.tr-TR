---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727415"
---
# <a name="rangestart-function"></a><span data-ttu-id="db879-102">RangeStart işlevi</span><span class="sxs-lookup"><span data-stu-id="db879-102">RangeStart function</span></span>

<span data-ttu-id="db879-103">Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="db879-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="db879-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="db879-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="db879-105">Verilen aralığın tanımlanan başlangıç değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="db879-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="db879-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="db879-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="db879-107">Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="db879-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="db879-108">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db879-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db879-109">Verilen aralığın tanımlanan başlangıç değeri.</span><span class="sxs-lookup"><span data-stu-id="db879-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="db879-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="db879-110">Remarks</span></span>

<span data-ttu-id="db879-111">Aralık ifadesinin ilk öğesi `start` , ikinci öğesi ise, `start+step` üçüncü öğe, `start+step+step` vb. olur `end` .</span><span class="sxs-lookup"><span data-stu-id="db879-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="db879-112">Aralık boş bir sıra belirtmediği sürece bir aralığın tanımlanan başlangıç değerinin sıranın ilk öğesiyle aynı olduğunu unutmayın (örneğin, 2..</span><span class="sxs-lookup"><span data-stu-id="db879-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="db879-113">1).</span><span class="sxs-lookup"><span data-stu-id="db879-113">1).</span></span>