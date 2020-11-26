---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: ApplyCCNOTChain işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: 275f31ea636d15eb0d78e5148e8af6b58d22729d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209664"
---
# <a name="applyccnotchain-operation"></a>ApplyCCNOTChain işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


, Yazmaçların bir sonraki qubit ' i üzerinde işlem gören iki qubit kayıt 'nin karşılık gelen bitleri üzerinde denetlenen CCNOT kapıları basamaklandırmasını uygular.
Her iki kasada de 0 konumundaki qubits 'lerden başlayarak, CCNOT hedef yazmacın 1. konumunda ve ardından hedef kayıttaki qubits 'e, vb. konumdaki qubitlere göre kontrol edilir ve hedef kasada bir eylemle biter `Length(nQubits)-1` .

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="register--qubit"></a>kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit yazmaç, yalnızca denetimler için kullanılır.


### <a name="targets--qubit"></a>hedefler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit yazmaç, denetimler ve hedef olarak kullanılır.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Hedef qubit kayıt, diğer kayıt özelliğinden daha fazla bir qubit olmalıdır.