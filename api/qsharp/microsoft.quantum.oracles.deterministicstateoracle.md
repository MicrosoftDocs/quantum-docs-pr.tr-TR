---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6f8f80aacd3386ba61675101acb87e09fff5afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193939"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="a7ff5-102">DeterministicStateOracle Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="a7ff5-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="a7ff5-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="a7ff5-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="a7ff5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7ff5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7ff5-105">Belirleyici bir durum hazırlığı için Oracle 'ı temsil eder.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="a7ff5-106">Oracle $O $ ' e giriş:</span><span class="sxs-lookup"><span data-stu-id="a7ff5-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="a7ff5-107">İstenen hisse durumu $ \ket{\psı} s $ ' i depolayacak kayıt \_ .</span><span class="sxs-lookup"><span data-stu-id="a7ff5-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="a7ff5-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a7ff5-108">Remarks</span></span>

<span data-ttu-id="a7ff5-109">$O {0} \tus= \ket{\psı} $ tarafından tanımlanan bu Oracle, {0} $ \ket{\psı} $ durumunu oluşturmak için hesaplama tabanlı durum $ \tus$ üzerinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="a7ff5-110">İlk parametre, $ \ket{\psı} $ ' nin qubit kayıt dizinidir.</span><span class="sxs-lookup"><span data-stu-id="a7ff5-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>