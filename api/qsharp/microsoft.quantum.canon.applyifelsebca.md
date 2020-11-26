---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: ApplyIfElseBCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: d36b16298ea177f16b7bbb260f069bfe35b9a72f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218640"
---
# <a name="applyifelsebca-operation"></a>ApplyIfElseBCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Klasik bitin değerine bağlı olarak iki Unitary işlemden birini uygular.

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

Bir bit verildiğinde, `bit` `trueOp` `trueInput` ,, olduğu zaman girişi olarak ile işlemini `bit` uygular `true` ve `falseOp(falseInput)` ne zaman geçerlidir `bit` `false` .

## <a name="input"></a>Giriş

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

`trueOp`Veya uygulanıp uygulanmadığını belirlemede kullanılan Boolean değeri `falseOp` .


### <a name="trueop--t--unit--is-adj--ctl"></a>trueOp: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Olduğunda uygulanacak Unitary işlemi `bit` `true` .


### <a name="trueinput--t"></a>Trueınput: 'T

Olduğunda olarak sağlanacak giriş `trueOp` `bit` `true` .


### <a name="falseop--u--unit--is-adj--ctl"></a>Yanlışop: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Olduğunda uygulanacak Unitary işlemi `bit` `false` .


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