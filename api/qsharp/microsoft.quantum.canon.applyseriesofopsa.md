---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e5b3527507f79dcc77803ce01472856145df0e9f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217977"
---
# <a name="applyseriesofopsa-operation"></a>ApplySeriesOfOpsA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir dizi üzerinde sırayla Ops ve hedefleri listesini uygular. (Adjoint)

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a>Giriş

### <a name="listofops--t--unit--is-adj"></a>Lıfops: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı []

Her biri bir 'T dizisi alan Ops listesi, uygulanacak. Bunlar sırasıyla, önce en düşük dizin olarak uygulanır.
Her birinin bir adjoint functor 'ı olmalıdır


### <a name="targets--int"></a>hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []

Op 'ın hedeflerini tanımlayan iç içe diziler. Her dizi, kullanılacak dizinleri açıklayan bir liste içermelidir.


### <a name="register--t"></a>kaydolun: 'T []

Üzerinde işlem yapmak için qubit kaydolun.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)