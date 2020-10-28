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
# <a name="rangestart-function"></a>RangeStart işlevi

Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)

Leyebilir [](https://nuget.org/packages/)


Verilen aralığın tanımlanan başlangıç değerini döndürür.

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a>Giriş

### <a name="range--range"></a>Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Verilen aralığın tanımlanan başlangıç değeri.

## <a name="remarks"></a>Açıklamalar

Aralık ifadesinin ilk öğesi `start` , ikinci öğesi ise, `start+step` üçüncü öğe, `start+step+step` vb. olur `end` .

Aralık boş bir sıra belirtmediği sürece bir aralığın tanımlanan başlangıç değerinin sıranın ilk öğesiyle aynı olduğunu unutmayın (örneğin, 2.. 1).