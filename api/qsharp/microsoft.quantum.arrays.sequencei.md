---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220306"
---
# <a name="sequencei-function"></a>SequenceI işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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