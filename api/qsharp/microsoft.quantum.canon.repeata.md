---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5f418f67d7265d4cb39b3636906c74d33d80f472
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205567"
---
# <a name="repeata-operation"></a>RepeatA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi verilen sayıda yineler.

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a>Giriş

### <a name="op--tinput--unit--is-adj"></a>Op: ' TInput => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

İşlemin tekrar çağrılması.


### <a name="ntimes--int"></a>nTimes: [Int](xref:microsoft.quantum.lang-ref.int)

Çağrılacak zaman sayısı `op` .


### <a name="input--tinput"></a>Giriş: ' TInput

Geçirilecek giriş `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="tinput"></a>' TInput



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. DrawMany](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Microsoft. hisse. Canon. Repeat](xref:Microsoft.Quantum.Canon.Repeat)
- [Microsoft. hisse. Canon. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)
- [Microsoft. hisse. Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)