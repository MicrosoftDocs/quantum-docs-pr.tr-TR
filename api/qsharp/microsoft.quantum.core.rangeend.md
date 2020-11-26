---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 90a9e31bf5c4a5e92a35998ddaec8c9e9de9888e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224046"
---
# <a name="rangeend-function"></a><span data-ttu-id="e19a0-102">RangeEnd işlevi</span><span class="sxs-lookup"><span data-stu-id="e19a0-102">RangeEnd function</span></span>

<span data-ttu-id="e19a0-103">Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="e19a0-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="e19a0-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e19a0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e19a0-105">Belirtilen aralığın, dizideki son öğe olması gereken tanımlı bitiş değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="e19a0-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="e19a0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e19a0-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="e19a0-107">Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="e19a0-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="e19a0-108">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e19a0-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e19a0-109">Verilen aralığın tanımlı bitiş değeri.</span><span class="sxs-lookup"><span data-stu-id="e19a0-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="e19a0-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e19a0-110">Remarks</span></span>

<span data-ttu-id="e19a0-111">Aralık ifadesinin ilk öğesi `start` , ikinci öğesi ise, `start+step` üçüncü öğe, `start+step+step` vb. olur `end` .</span><span class="sxs-lookup"><span data-stu-id="e19a0-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="e19a0-112">Bir aralığın tanımlanan bitiş değerinin, Aralık tarafından belirtilen dizideki son öğeden farklı olabileceğini unutmayın; Örneğin, 0 aralığında.</span><span class="sxs-lookup"><span data-stu-id="e19a0-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="e19a0-113">2..</span><span class="sxs-lookup"><span data-stu-id="e19a0-113">2 ..</span></span> <span data-ttu-id="e19a0-114">5 son öğe 4, ancak bitiş değeri 5 ' tir.</span><span class="sxs-lookup"><span data-stu-id="e19a0-114">5 the last element is 4 but the end value is 5.</span></span>