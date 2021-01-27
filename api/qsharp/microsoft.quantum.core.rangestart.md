---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831110"
---
# <a name="rangestart-function"></a><span data-ttu-id="33deb-102">RangeStart işlevi</span><span class="sxs-lookup"><span data-stu-id="33deb-102">RangeStart function</span></span>

<span data-ttu-id="33deb-103">Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="33deb-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="33deb-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="33deb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="33deb-105">Verilen aralığın tanımlanan başlangıç değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="33deb-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="33deb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="33deb-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="33deb-107">Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="33deb-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="33deb-108">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="33deb-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="33deb-109">Verilen aralığın tanımlanan başlangıç değeri.</span><span class="sxs-lookup"><span data-stu-id="33deb-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="33deb-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="33deb-110">Remarks</span></span>

<span data-ttu-id="33deb-111">Aralık ifadesinin ilk öğesi `start` , ikinci öğesi ise, `start+step` üçüncü öğe, `start+step+step` vb. olur `end` .</span><span class="sxs-lookup"><span data-stu-id="33deb-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="33deb-112">Aralık boş bir sıra belirtmediği sürece bir aralığın tanımlanan başlangıç değerinin sıranın ilk öğesiyle aynı olduğunu unutmayın (örneğin, 2..</span><span class="sxs-lookup"><span data-stu-id="33deb-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="33deb-113">1).</span><span class="sxs-lookup"><span data-stu-id="33deb-113">1).</span></span>