---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: ApplyIfZero işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 215b71a8d2e4f8a22df05b210824bc40a969b6f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841736"
---
# <a name="applyifzero-operation"></a>ApplyIfZero işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Klasik sonuç değeri sıfır olan bir işlem uygular.

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a>Description

Bir işlem `op` ve sonuç değeri verildiğinde, `result` if ise `op` için geçerlidir `target` `result` `Zero` . Varsa, `One` hiçbir şey olmaz `target` .

## <a name="input"></a>Giriş

### <a name="result--__invalidresult__"></a>Sonuç: __geçersiz <Result>__

Op 'ın uygulanıp uygulanmadığını denetleyen ölçüm sonucu.


### <a name="op--t--unit"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) 

Koşullu olarak uygulanacak bir işlem.


### <a name="target--t"></a>Hedef: 'T

İşlemin uygulandığı giriş.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Koşullu olarak uygulanacak işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Applyifsıfırlaması c](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [Microsoft. hisse. Canon. Applyifsıfırlaması a](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [Microsoft. hisse. Canon. ApplyIfZeroCA](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)