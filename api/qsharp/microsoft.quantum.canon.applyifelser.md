---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: ApplyIfElseR işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 0d7cc9f67f9dd0c69a9256f007a3aeab3e457907
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841806"
---
# <a name="applyifelser-operation"></a>ApplyIfElseR işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Klasik sonucun değerine bağlı olarak iki işlemden birini uygular.

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a>Description

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