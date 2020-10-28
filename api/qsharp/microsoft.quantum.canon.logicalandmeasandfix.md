---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728597"
---
# <a name="logicalandmeasandfix-operation"></a>LogicalANDMeasAndFix işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Birden çok qubits 'in mantıksal ve ' lerini hesaplar.

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>Giriş

### <a name="ctrlregister--qubit"></a>ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Birden çok giriş ve ağ geçidi için qubits girişi.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

VE çıktısının yazıldığı qubit. Bu durumun her zaman $ \ket $ durumunda başlaması varsayılır {0} .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

`ctrlRegister`Tam olarak $2 $ qubit 'e sahip olduğunda, bu işlem ile eşdeğerdir ancak $ \ket $ ve $ `CCNOT` {001} -e ^ {ı \ pi/2} $ üzerinde $ \ket $ {101} ve $ \ket $ üzerinde ^ {i \ pi/2} $ $e aşama ile olan aşama {011} .
Adjoint Ayrıca yalnızca özel durumlarda (başvuruları gör) özgün işlemin tersi olan ölçü ve düzeltme yaklaşımına sahiptir, ancak daha az T-Gates kullanır.

## <a name="references"></a>Referanslar

- [*Craig Gidney* , 1709,06648](https://arxiv.org/abs/1709.06648)