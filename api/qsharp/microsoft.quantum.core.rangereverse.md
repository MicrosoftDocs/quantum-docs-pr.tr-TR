---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853651"
---
# <a name="rangereverse-function"></a>RangeReverse işlevi

Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Giriş aralığının tersine çevrilmiş yeni bir Aralık döndürür.

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a>Giriş

### <a name="r--range"></a>r: [Range](xref:microsoft.quantum.lang-ref.range)

Giriş aralığı.



## <a name="output--range"></a>Çıkış: [Aralık](xref:microsoft.quantum.lang-ref.range)

Verilen aralığın tersine çevrilmiş yeni bir Aralık.

## <a name="remarks"></a>Açıklamalar

Bir `end` `-step` `start` aralığın gerçek son öğesi ile aynı olamaz, bir aralığın ters çevrilmesinin yalnızca.... olduğunu `end` unutmayın.