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
# <a name="rangestep-function"></a>RangeStep işlevi

Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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