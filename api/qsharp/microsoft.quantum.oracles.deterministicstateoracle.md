---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 10ae9e52f298cdfb92dd6a9e5cf85960bece6800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842584"
---
# <a name="deterministicstateoracle-user-defined-type"></a>DeterministicStateOracle Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirleyici bir durum hazırlığı için Oracle 'ı temsil eder.

Oracle $O $ ' e giriş:

- İstenen hisse durumu $ \ket{\psı} s $ ' i depolayacak kayıt \_ .

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Açıklamalar

$O {0} \tus= \ket{\psı} $ tarafından tanımlanan bu Oracle, {0} $ \ket{\psı} $ durumunu oluşturmak için hesaplama tabanlı durum $ \tus$ üzerinde çalışır.
İlk parametre, $ \ket{\psı} $ ' nin qubit kayıt dizinidir.