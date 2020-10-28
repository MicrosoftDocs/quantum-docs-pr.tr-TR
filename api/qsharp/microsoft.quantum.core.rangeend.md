---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727446"
---
# <a name="rangeend-function"></a><span data-ttu-id="97259-102">RangeEnd işlevi</span><span class="sxs-lookup"><span data-stu-id="97259-102">RangeEnd function</span></span>

<span data-ttu-id="97259-103">Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="97259-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="97259-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="97259-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="97259-105">Belirtilen aralığın, dizideki son öğe olması gereken tanımlı bitiş değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="97259-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="97259-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="97259-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="97259-107">Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="97259-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="97259-108">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97259-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97259-109">Verilen aralığın tanımlı bitiş değeri.</span><span class="sxs-lookup"><span data-stu-id="97259-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="97259-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="97259-110">Remarks</span></span>

<span data-ttu-id="97259-111">Aralık ifadesinin ilk öğesi `start` , ikinci öğesi ise, `start+step` üçüncü öğe, `start+step+step` vb. olur `end` .</span><span class="sxs-lookup"><span data-stu-id="97259-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="97259-112">Bir aralığın tanımlanan bitiş değerinin, Aralık tarafından belirtilen dizideki son öğeden farklı olabileceğini unutmayın; Örneğin, 0 aralığında.</span><span class="sxs-lookup"><span data-stu-id="97259-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="97259-113">2..</span><span class="sxs-lookup"><span data-stu-id="97259-113">2 ..</span></span> <span data-ttu-id="97259-114">5 son öğe 4, ancak bitiş değeri 5 ' tir.</span><span class="sxs-lookup"><span data-stu-id="97259-114">5 the last element is 4 but the end value is 5.</span></span>