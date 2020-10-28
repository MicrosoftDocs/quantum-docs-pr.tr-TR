---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: b68c3aa4298fffa76f7c43ac4c6d27cdf3b72fbf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728435"
---
# <a name="repeatca-operation"></a>RepeatCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir işlemi verilen sayıda yineler.

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>Giriş

### <a name="op--tinput--unit-adj--ctl"></a>Op: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL

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
- [Microsoft. hisse. Canon. RepeatA](xref:Microsoft.Quantum.Canon.RepeatA)
- [Microsoft. hisse. Canon. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)