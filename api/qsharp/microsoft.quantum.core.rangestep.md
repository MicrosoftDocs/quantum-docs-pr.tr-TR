---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727410"
---
# <a name="rangestep-function"></a><span data-ttu-id="438e8-102">RangeStep işlevi</span><span class="sxs-lookup"><span data-stu-id="438e8-102">RangeStep function</span></span>

<span data-ttu-id="438e8-103">Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="438e8-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="438e8-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="438e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="438e8-105">Bir aralığın sonraki değerinin nasıl hesaplanacağını belirten tamsayıyı döndürür.</span><span class="sxs-lookup"><span data-stu-id="438e8-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="438e8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="438e8-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="438e8-107">Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="438e8-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="438e8-108">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="438e8-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="438e8-109">Verilen aralığın tanımlı adım değeri.</span><span class="sxs-lookup"><span data-stu-id="438e8-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="438e8-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="438e8-110">Remarks</span></span>

<span data-ttu-id="438e8-111">Aralık ifadesinin ilk öğesi `start` , ikinci öğesi ise, `start+step` üçüncü öğe, `start+step+step` vb. olur `end` .</span><span class="sxs-lookup"><span data-stu-id="438e8-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>