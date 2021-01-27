---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: ApplyIfOne işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: b86aecf3dc3d02d1a6bf0c112bdc45a55a2cf087
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841775"
---
# <a name="applyifone-operation"></a>ApplyIfOne işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Klasik sonuç değeri bir olan bir işlem uygular.

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a>Description

Bir işlem `op` ve sonuç değeri verildiğinde, `result` if ise `op` için geçerlidir `target` `result` `One` . Varsa, `Zero` hiçbir şey olmaz `target` .

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

- [Microsoft. hisse. Canon. ApplyIfOneC](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [Microsoft. hisse. Canon. ApplyIfOneA](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [Microsoft. hisse. Canon. ApplyIfOneCA](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)