---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 793e72af56e288f9b437302f9958665e92e5e763
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842555"
---
# <a name="obliviousoracle-user-defined-type"></a>ObliviousOracle Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir Oracle 'ın yükümlülüğü en çok genliğini temsil eder.

Oracle $O $ girdileri şunlardır:

- Anyükleyen La, $O $ 'ın üzerinde davranması $a $.
- İstenen Unitary $U $ ' in uygulandığı $s $, kayıt sonrasında $ \ket{t} a $ konumundaki $a $ konumunda seçili olan sistem kaydı \_ .

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Açıklamalar

Bu Oracle tarafından tanımlanan bu Oracle $ $ O\ket {s} \_ a\ket {\ PSI} \_ s = \lambda\ket{t} \_ a U \ket{\psı} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cnoktalara $ $, $ \_ \ket{t} a $ tarafından işaretlenen temelinde her türlü sistem durumu $ \ket{\psi} \_ s $, genlik $ \lambda $ olan herhangi bir sistem durumunda Unitary $U $ ' i uygulamak için ansınla State $ \ket{s} a $ üzerinde çalışır \_ .
İlk parametre $ \ket{s} a $ 'ın qubit kayıt dizinidir \_ . İkinci parametre, $ \ket{\psı} s $ ' nin qubit kayıt dizinidir \_ .