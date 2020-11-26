---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: ApplyIfElseBC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: ea06b0a0a07659407e13caa2baa4f3e37ca2a0f7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209528"
---
# <a name="applyifelsebc-operation"></a>ApplyIfElseBC işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Klasik bir bitin değerine bağlı olarak, iki denetlenebilir işlemden birini uygular.

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit is Ctl
```


## <a name="description"></a>Açıklama

Bir bit verildiğinde, `bit` `trueOp` `trueInput` ,, olduğu zaman girişi olarak ile işlemini `bit` uygular `true` ve `falseOp(falseInput)` ne zaman geçerlidir `bit` `false` .

## <a name="input"></a>Giriş

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

`trueOp`Veya uygulanıp uygulanmadığını belirlemede kullanılan Boolean değeri `falseOp` .


### <a name="trueop--t--unit--is-ctl"></a>trueOp: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL

Olduğunda uygulanacak denetlenebilir işlem `bit` `true` .


### <a name="trueinput--t"></a>Trueınput: 'T

Olduğunda olarak sağlanacak giriş `trueOp` `bit` `true` .


### <a name="falseop--u--unit--is-ctl"></a>Yanlışop: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  CTL

Olduğunda uygulanacak denetlenebilir işlem `bit` `false` .


### <a name="falseinput--u"></a>Yanlışgiriş: ' U

Olduğunda olarak sağlanacak giriş `falseOp` `bit` `false` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Koşullu olarak uygulanacak işlemin giriş türü `trueOp` .
### <a name="u"></a>' U

Koşullu olarak uygulanacak işlemin giriş türü `falseOp` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. hisse. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. hisse. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. hisse. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. hisse. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)