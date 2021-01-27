---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841508"
---
# <a name="applyseriesofops-operation"></a>ApplySeriesOfOps işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir dizi üzerinde sırayla Ops ve hedefleri listesini uygular.

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="listofops--t--unit-"></a>Lıfops: 'T [] => [Unit](xref:microsoft.quantum.lang-ref.unit) []

Her biri bir 'T dizisi alan Ops listesi, uygulanacak. Bunlar sırasıyla, önce en düşük dizin olarak uygulanır.


### <a name="targets--int"></a>hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []

Op 'ın hedeflerini tanımlayan iç içe diziler. Her dizi, kullanılacak dizinleri açıklayan bir liste içermelidir.


### <a name="register--t"></a>kaydolun: 'T []

Üzerinde işlem yapmak için qubit kaydolun.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="example"></a>Örnek

Aşağıdakiler, exp ([PauliX, PauliY], 0,5) ile qubits 0, 1//then X-qubit 2 Let Ops = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubit (X, _)]; için geçerlidir. Let dizinleri = [[0, 1], [2]]; ApplySeriesOfOps (Ops, dizinler, qubitArray);

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)