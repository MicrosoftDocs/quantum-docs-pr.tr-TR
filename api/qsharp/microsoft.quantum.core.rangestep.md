---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853608"
---
# <a name="rangestep-function"></a><span data-ttu-id="0b77a-102">RangeStep işlevi</span><span class="sxs-lookup"><span data-stu-id="0b77a-102">RangeStep function</span></span>

<span data-ttu-id="0b77a-103">Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="0b77a-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="0b77a-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0b77a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0b77a-105">Bir aralığın sonraki değerinin nasıl hesaplanacağını belirten tamsayıyı döndürür.</span><span class="sxs-lookup"><span data-stu-id="0b77a-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="0b77a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0b77a-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="0b77a-107">Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="0b77a-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="0b77a-108">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0b77a-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0b77a-109">Verilen aralığın tanımlı adım değeri.</span><span class="sxs-lookup"><span data-stu-id="0b77a-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b77a-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0b77a-110">Remarks</span></span>

<span data-ttu-id="0b77a-111">Aralık ifadesinin ilk öğesi `start` , ikinci öğesi ise, `start+step` üçüncü öğe, `start+step+step` vb. olur `end` .</span><span class="sxs-lookup"><span data-stu-id="0b77a-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>