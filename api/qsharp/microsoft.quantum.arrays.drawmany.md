---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210004"
---
# <a name="drawmany-operation"></a>DrawMany işlemi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi belirli sayıda örnek için yineler ve çıktılarını bir dizide toplar.

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a>Giriş

### <a name="op--tinput--toutput"></a>Op: ' TInput => ' TOutput 

İşlemin tekrar çağrılması.


### <a name="nsamples--int"></a>nSamples: [Int](xref:microsoft.quantum.lang-ref.int)

Toplanacak çağrı örnekleri sayısı `op` .


### <a name="input--tinput"></a>Giriş: ' TInput

Geçirilecek giriş `op` .



## <a name="output--toutput"></a>Çıkış: ' TOutput []



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="tinput"></a>' TInput


### <a name="toutput"></a>' TOutput



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Repeat](xref:Microsoft.Quantum.Canon.Repeat)