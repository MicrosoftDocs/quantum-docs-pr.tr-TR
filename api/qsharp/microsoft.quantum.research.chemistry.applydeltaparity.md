---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Applydeltaeşliği işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: bb01eb684ff1820be08a573c0ca6cfc12efeb889
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733207"
---
# <a name="applydeltaparity-operation"></a>Applydeltaeşliği işlemi

Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Leyebilir [](https://nuget.org/packages/)


Önceki bir PQRS arasındaki eşlik farkını hesaplar... hüküm ve sonraki PQRS... terimli. Bu fark, bir yardımcı qubit üzerinde hesaplanır.

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="prevfermionicterm--int"></a>Prevfermıonicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]

Önceki PQRS için dizinlerin listesi... larındaki.


### <a name="nextfermionicterm--int"></a>Nextfermıonicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]

Sonraki PQRS için dizinlerin listesi... larındaki.


### <a name="aux--qubit"></a>Aux: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Eşlik hesaplama sonuçlarının depolandığı yardımcı qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit, tüm PQRS tarafından üzerinde işlem yaptığı... larındaki.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu, P < Q < R < S 'nin dizinlerinin < olduğunu varsayar... hem prevPQ hem de nextPQ için.