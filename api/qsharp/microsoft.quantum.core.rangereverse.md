---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213846"
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