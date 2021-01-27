---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: ApplyOpRepeatedlyOverC işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 1cf3f32f0d25c1b4437f2bdbd93171a1a2e1e760
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844787"
---
# <a name="applyoprepeatedlyoverc-operation"></a>ApplyOpRepeatedlyOverC işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aynı op 'yi bir qubit kayıt için birden çok kez uygular.

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Giriş

### <a name="op--qubit--unit--is-ctl"></a>Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL

Qubit kaydına birden çok kez uygulanacak bir işlem


### <a name="targets--int"></a>hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []

Op 'ın hedeflerini tanımlayan iç içe diziler. Her dizi, kullanılacak qubits 'i açıklayan bir liste içermelidir.


### <a name="register--qubit"></a>kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Üzerinde işlem yapmak için qubit kaydolun.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplySeriesOfOps](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)