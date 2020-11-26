---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220272"
---
# <a name="sequencel-function"></a>SequenceL işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Verilen bir aralıktaki tamsayıların dizisini alır.

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>Giriş

### <a name="from--bigint"></a>Kimden: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Aralığın kapsamlı başlangıç dizini.


### <a name="to--bigint"></a>Şu şekilde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Aralıktan küçük olmayan aralığın kapsamlı bir bitiş dizini `from` .



## <a name="output--bigint"></a>Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]

Sayı dizisini içeren bir dizi `from` , `from + 1` ,..., `to` .

## <a name="remarks"></a>Açıklamalar

Ve arasındaki fark `from` `to` bir değere sığması gerekir `Int` .