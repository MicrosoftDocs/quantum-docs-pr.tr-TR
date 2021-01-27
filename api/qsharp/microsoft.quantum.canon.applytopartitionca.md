---
uid: Microsoft.Quantum.Canon.ApplyToPartitionCA
title: ApplyToPartitionCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionCA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 572cf824647b3e7f7c0e17c797d519f41914f79d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841277"
---
# <a name="applytopartitionca-operation"></a>ApplyToPartitionCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir kaydın belirli bir bölümüne iki bölümden bir işlem çifti uygular.
Değiştirici, `CA` işlemin denetlenebilir ve adjointable olduğunu gösterir.

```qsharp
operation ApplyToPartitionCA (op : ((Qubit[], Qubit[]) => Unit is Ctl + Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="op--qubitqubit--unit--is-adj--ctl"></a>Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Verilen bölüme uygulanacak işlem çifti.


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument: [Int](xref:microsoft.quantum.lang-ref.int)

Hedeften itibaren bölümün ilk kısmına yerleştirilecek qubits sayısı.
Kalan qubits, bölümün ikinci bölümünü oluşturur.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Bölümlenen ve belirtilen iki işlem tarafından çalıştırılan bir qubits kaydı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToPartition](xref:Microsoft.Quantum.Canon.ApplyToPartition)