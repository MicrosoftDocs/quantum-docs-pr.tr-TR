---
uid: Microsoft.Quantum.Canon.ApplyToPartitionA
title: ApplyToPartitionA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 79f8fbed1592670031b3348155cdd4000eadc1fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208357"
---
# <a name="applytopartitiona-operation"></a>ApplyToPartitionA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir kaydın belirli bir bölümüne iki bölümden bir işlem çifti uygular.
Değiştirici, `A` işlemin adjointable olduğunu gösterir.

```qsharp
operation ApplyToPartitionA (op : ((Qubit[], Qubit[]) => Unit is Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Giriş

### <a name="op--qubitqubit--unit--is-adj"></a>Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Verilen bölüme uygulanacak işlem çifti.


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument: [Int](xref:microsoft.quantum.lang-ref.int)

Hedeften itibaren bölümün ilk kısmına yerleştirilecek qubits sayısı.
Kalan qubits, bölümün ikinci bölümünü oluşturur.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Bölümlenen ve belirtilen iki işlem tarafından çalıştırılan bir qubits kaydı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToPartition](xref:Microsoft.Quantum.Canon.ApplyToPartition)