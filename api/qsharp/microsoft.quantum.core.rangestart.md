---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 44683b204ecd469f5f5412a7ec06e98ec8a4f37e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224012"
---
# <a name="rangestart-function"></a><span data-ttu-id="1e0bc-102">RangeStart işlevi</span><span class="sxs-lookup"><span data-stu-id="1e0bc-102">RangeStart function</span></span>

<span data-ttu-id="1e0bc-103">Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="1e0bc-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="1e0bc-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1e0bc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1e0bc-105">Verilen aralığın tanımlanan başlangıç değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="1e0bc-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="1e0bc-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1e0bc-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="1e0bc-107">Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="1e0bc-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="1e0bc-108">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1e0bc-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1e0bc-109">Verilen aralığın tanımlanan başlangıç değeri.</span><span class="sxs-lookup"><span data-stu-id="1e0bc-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e0bc-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1e0bc-110">Remarks</span></span>

<span data-ttu-id="1e0bc-111">Aralık ifadesinin ilk öğesi `start` , ikinci öğesi ise, `start+step` üçüncü öğe, `start+step+step` vb. olur `end` .</span><span class="sxs-lookup"><span data-stu-id="1e0bc-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="1e0bc-112">Aralık boş bir sıra belirtmediği sürece bir aralığın tanımlanan başlangıç değerinin sıranın ilk öğesiyle aynı olduğunu unutmayın (örneğin, 2..</span><span class="sxs-lookup"><span data-stu-id="1e0bc-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="1e0bc-113">1).</span><span class="sxs-lookup"><span data-stu-id="1e0bc-113">1).</span></span>