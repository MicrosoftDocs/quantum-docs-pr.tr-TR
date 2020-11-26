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
# <a name="rangestart-function"></a>RangeStart işlevi

Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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