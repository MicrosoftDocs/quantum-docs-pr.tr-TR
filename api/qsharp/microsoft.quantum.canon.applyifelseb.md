---
uid: Microsoft.Quantum.Canon.ApplyIfElseB
title: ApplyIfElseB işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseB
qsharp.summary: Applies one of two operations, depending on the value of a classical bit.
ms.openlocfilehash: 68c06a5141b9ff423c2d18adc3a9e162eed939f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729583"
---
# <a name="applyifelseb-operation"></a>ApplyIfElseB işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Klasik bitin değerine bağlı olarak iki işlemden birini uygular.

```qsharp
operation ApplyIfElseB<'T, 'U> (bit : Bool, (trueOp : ('T => Unit), trueInput : 'T), (falseOp : ('U => Unit), falseInput : 'U)) : Unit
```


## <a name="description"></a>Açıklama

Bir bit verildiğinde, `bit` `trueOp` `trueInput` ,, olduğu zaman girişi olarak ile işlemini `bit` uygular `true` ve `falseOp(falseInput)` ne zaman geçerlidir `bit` `false` .

## <a name="input"></a>Giriş

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

`trueOp`Veya uygulanıp uygulanmadığını belirlemede kullanılan Boolean değeri `falseOp` .


### <a name="trueop--t--unit"></a>trueOp: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) 

Ne zaman uygulanacak işlem `bit` `true` .


### <a name="trueinput--t"></a>Trueınput: 'T

Olduğunda olarak sağlanacak giriş `trueOp` `bit` `true` .


### <a name="falseop--u--unit"></a>Yanlışop: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit) 

Ne zaman uygulanacak işlem `bit` `false` .


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