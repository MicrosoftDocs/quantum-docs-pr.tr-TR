---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727440"
---
# <a name="rangereverse-function"></a>RangeReverse işlevi

Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)

Leyebilir [](https://nuget.org/packages/)


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