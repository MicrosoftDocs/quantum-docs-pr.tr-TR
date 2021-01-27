---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: af93220562d6be27b2f41e770bd953e5e808fcbf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852202"
---
# <a name="repeatca-operation"></a>RepeatCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi verilen sayıda yineler.

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="op--tinput--unit--is-adj--ctl"></a>Op: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  , ayarlanabilir ve CTL

İşlemin tekrar çağrılması.


### <a name="ntimes--int"></a>nTimes: [Int](xref:microsoft.quantum.lang-ref.int)

Çağrılacak zaman sayısı `op` .


### <a name="input--tinput"></a>Giriş: ' TInput

Geçirilecek giriş `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="tinput"></a>' TInput



## <a name="example"></a>Örnek

Aşağıdakiler eşdeğerdir:

```qsharp
RepeatCA(U, 17, target);
(BoundCA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. DrawMany](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Microsoft. hisse. Canon. Repeat](xref:Microsoft.Quantum.Canon.Repeat)
- [Microsoft. hisse. Canon. RepeatA](xref:Microsoft.Quantum.Canon.RepeatA)
- [Microsoft. hisse. Canon. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)