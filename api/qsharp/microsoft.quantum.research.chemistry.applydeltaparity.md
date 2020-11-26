---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Applydeltaeşliği işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: 40157b6a166b09c6fee63d86e203f92069d008f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225763"
---
# <a name="applydeltaparity-operation"></a>Applydeltaeşliği işlemi

Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Paket: [Microsoft. hisse. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Önceki bir PQRS arasındaki eşlik farkını hesaplar... hüküm ve sonraki PQRS... terimli. Bu fark, bir yardımcı qubit üzerinde hesaplanır.

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
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