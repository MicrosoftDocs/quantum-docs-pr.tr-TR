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
# <a name="rangestep-function"></a>RangeStep işlevi

Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)

Leyebilir [](https://nuget.org/packages/)


Bir aralığın sonraki değerinin nasıl hesaplanacağını belirten tamsayıyı döndürür.

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a>Giriş

### <a name="range--range"></a>Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Verilen aralığın tanımlı adım değeri.

## <a name="remarks"></a>Açıklamalar

Aralık ifadesinin ilk öğesi `start` , ikinci öğesi ise, `start+step` üçüncü öğe, `start+step+step` vb. olur `end` .