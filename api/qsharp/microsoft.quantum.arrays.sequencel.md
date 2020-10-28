---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730023"
---
# <a name="sequencel-function"></a>SequenceL işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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