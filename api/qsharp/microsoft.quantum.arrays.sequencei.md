---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730034"
---
# <a name="sequencei-function"></a>SequenceI işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


Verilen bir aralıktaki tamsayıların dizisini alır.

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a>Giriş

### <a name="from--int"></a>Kimden: [Int](xref:microsoft.quantum.lang-ref.int)

Aralığın kapsamlı başlangıç dizini.


### <a name="to--int"></a>to: [Int](xref:microsoft.quantum.lang-ref.int)

Aralıktan küçük olmayan aralığın kapsamlı bir bitiş dizini `from` .



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]

Sayı dizisini içeren bir dizi `from` , `from + 1` ,..., `to` .