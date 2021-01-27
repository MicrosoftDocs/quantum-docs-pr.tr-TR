---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9a1f6189428b086c38b1d0f289afb18c2cf1be40
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850862"
---
# <a name="applyseriesofopsca-operation"></a>ApplySeriesOfOpsCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir dizi üzerinde sırayla Ops ve hedefleri listesini uygular. (Adjoint + denetimli)

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="listofops--t--unit--is-adj--ctl"></a>Lıfops: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL []

Her biri bir 'T dizisi alan Ops listesi, uygulanacak. Bunlar sırasıyla, önce en düşük dizin olarak uygulanır.
Her birinin hem adjoint hem de denetimli bir functor 'a sahip olması gerekir.


### <a name="targets--int"></a>hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []

Op 'ın hedeflerini tanımlayan iç içe diziler. Her dizi, kullanılacak dizinleri açıklayan bir liste içermelidir.


### <a name="register--t"></a>kaydolun: 'T []

Üzerinde işlem yapmak için qubit kaydolun.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="example"></a>Örnek

Aşağıdaki, exp ([PauliX, PauliY], 0,5) ile qubits 0, 1//ve X-qubit 2 Let Ops = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubitCA (X, _)]; için geçerlidir. Let dizinleri = [[0, 1], [2]]; ApplySeriesOfOpsCA (Ops, dizinler, qubitArray);

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)