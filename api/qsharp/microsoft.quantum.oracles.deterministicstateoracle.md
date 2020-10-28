---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: f02267d48cf42fb5b02782dc6b667ac7b60a05dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733386"
---
# <a name="deterministicstateoracle-user-defined-type"></a>DeterministicStateOracle Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Leyebilir [](https://nuget.org/packages/)


Belirleyici bir durum hazırlığı için Oracle 'ı temsil eder.

Oracle $O $ ' e giriş:

- İstenen hisse durumu $ \ket{\psı} s $ ' i depolayacak kayıt \_ .

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Açıklamalar

$O {0} \tus= \ket{\psı} $ tarafından tanımlanan bu Oracle, {0} $ \ket{\psı} $ durumunu oluşturmak için hesaplama tabanlı durum $ \tus$ üzerinde çalışır.
İlk parametre, $ \ket{\psı} $ ' nin qubit kayıt dizinidir.