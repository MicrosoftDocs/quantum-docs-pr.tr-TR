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
# <a name="rangeend-function"></a>RangeEnd işlevi

Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)

Leyebilir [](https://nuget.org/packages/)


Belirtilen aralığın, dizideki son öğe olması gereken tanımlı bitiş değerini döndürür.

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a>Giriş

### <a name="range--range"></a>Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Verilen aralığın tanımlı bitiş değeri.

## <a name="remarks"></a>Açıklamalar

Aralık ifadesinin ilk öğesi `start` , ikinci öğesi ise, `start+step` üçüncü öğe, `start+step+step` vb. olur `end` .

Bir aralığın tanımlanan bitiş değerinin, Aralık tarafından belirtilen dizideki son öğeden farklı olabileceğini unutmayın; Örneğin, 0 aralığında. 2.. 5 son öğe 4, ancak bitiş değeri 5 ' tir.