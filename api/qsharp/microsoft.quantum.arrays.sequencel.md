---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850980"
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

## <a name="example"></a>Örnek

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a>Açıklamalar

Ve arasındaki fark `from` `to` bir değere sığması gerekir `Int` .