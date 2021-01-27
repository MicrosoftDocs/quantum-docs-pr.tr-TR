---
uid: Microsoft.Quantum.Canon.Repeat
title: İşlemi yinele
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 40ee191e8d9044f33aa1621303c70f7e0847e8f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852238"
---
# <a name="repeat-operation"></a>İşlemi yinele

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi verilen sayıda yineler.

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>Giriş

### <a name="op--tinput--unit"></a>Op: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) 

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
Repeat(U, 17, target);
(Bound(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. DrawMany](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Microsoft. hisse. Canon. RepeatA](xref:Microsoft.Quantum.Canon.RepeatA)
- [Microsoft. hisse. Canon. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)
- [Microsoft. hisse. Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)