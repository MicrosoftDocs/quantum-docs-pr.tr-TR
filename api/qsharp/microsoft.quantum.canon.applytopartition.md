---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: ApplyToPartition işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: a0dc3453e7501816132569869e858418d5f3f4e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850550"
---
# <a name="applytopartition-operation"></a>ApplyToPartition işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir kaydın belirli bir bölümüne iki bölümden bir işlem çifti uygular.

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="op--qubitqubit--unit"></a>Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Verilen bölüme uygulanacak işlem çifti.


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument: [Int](xref:microsoft.quantum.lang-ref.int)

Hedeften itibaren bölümün ilk kısmına yerleştirilecek qubits sayısı.
Kalan qubits, bölümün ikinci bölümünü oluşturur.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Bölümlenen ve belirtilen iki işlem tarafından çalıştırılan bir qubits kaydı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToPartitionA](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [Microsoft. hisse. Canon. ApplyToPartitionC](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [Microsoft. hisse. Canon. ApplyToPartitionCA](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)