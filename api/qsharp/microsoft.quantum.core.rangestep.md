---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 39c8581fe795a1b76d2a6e81c238a271287c2c38
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213812"
---
# <a name="rangestep-function"></a><span data-ttu-id="7879d-102">RangeStep işlevi</span><span class="sxs-lookup"><span data-stu-id="7879d-102">RangeStep function</span></span>

<span data-ttu-id="7879d-103">Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="7879d-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="7879d-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7879d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7879d-105">Bir aralığın sonraki değerinin nasıl hesaplanacağını belirten tamsayıyı döndürür.</span><span class="sxs-lookup"><span data-stu-id="7879d-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="7879d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7879d-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="7879d-107">Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="7879d-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="7879d-108">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7879d-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7879d-109">Verilen aralığın tanımlı adım değeri.</span><span class="sxs-lookup"><span data-stu-id="7879d-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="7879d-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7879d-110">Remarks</span></span>

<span data-ttu-id="7879d-111">Aralık ifadesinin ilk öğesi `start` , ikinci öğesi ise, `start+step` üçüncü öğe, `start+step+step` vb. olur `end` .</span><span class="sxs-lookup"><span data-stu-id="7879d-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>