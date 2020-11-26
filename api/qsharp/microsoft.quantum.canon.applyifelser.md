---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: ApplyIfElseR işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 874dae2ba5e842066e9c1582af431a73520e4ccd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209545"
---
# <a name="applyifelser-operation"></a>ApplyIfElseR işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Klasik sonucun değerine bağlı olarak iki işlemden birini uygular.

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a>Açıklama

Sonuç verildiğinde `result` , `zeroOp` `zeroInput` öğesine eşit olduğu zaman girişi olarak ile işlemi uygular `result` `Zero` ve `oneOp(oneInput)` ne zaman geçerlidir `result == One` .

## <a name="input"></a>Giriş

### <a name="result--__invalidresult__"></a>Sonuç: __geçersiz <Result>__

Ölçüm sonucu, veya uygulanmış olup olmadığını tespit etmek için kullanılır `zeroOp` `oneOp` .


### <a name="zeroop--t--unit"></a>Sıfırlama Işleci: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) 

Ne zaman uygulanacak işlem `result == Zero` .


### <a name="zeroinput--t"></a>Sıfırlama girişi: 'T

`zeroOp`Ne zaman sağlanacak giriş `result == Zero` .


### <a name="oneop--u--unit"></a>oneOp: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit) 

Ne zaman uygulanacak işlem `result == One` .


### <a name="oneinput--u"></a>Oneınput: ' U

`oneOp`Ne zaman sağlanacak giriş `result == One` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Koşullu olarak uygulanacak işlemin giriş türü `zeroOp` .
### <a name="u"></a>' U

Koşullu olarak uygulanacak işlemin giriş türü `oneOp` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. hisse. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. hisse. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. hisse. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. hisse. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)