---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: ApplyIfElseBA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: ce08907646c3210f76244f29aa0d936e2bd6ee43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729570"
---
# <a name="applyifelseba-operation"></a>ApplyIfElseBA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Klasik bir bit değerine bağlı olarak iki adjointable işlemden birini uygular.

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit
```


## <a name="description"></a>Açıklama

Bir bit verildiğinde, `bit` `trueOp` `trueInput` ,, olduğu zaman girişi olarak ile işlemini `bit` uygular `true` ve `falseOp(falseInput)` ne zaman geçerlidir `bit` `false` .

## <a name="input"></a>Giriş

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

`trueOp`Veya uygulanıp uygulanmadığını belirlemede kullanılan Boolean değeri `falseOp` .


### <a name="trueop--t--unit-adj"></a>trueOp: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması

Olduğunda uygulanacak adjointable işlemi `bit` `true` .


### <a name="trueinput--t"></a>Trueınput: 'T

Olduğunda olarak sağlanacak giriş `trueOp` `bit` `true` .


### <a name="falseop--u--unit-adj"></a>Yanlışop: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlaması

Olduğunda uygulanacak adjointable işlemi `bit` `false` .


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