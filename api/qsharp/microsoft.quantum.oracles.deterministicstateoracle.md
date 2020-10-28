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
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="ffee0-102">DeterministicStateOracle Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="ffee0-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="ffee0-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="ffee0-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="ffee0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ffee0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ffee0-105">Belirleyici bir durum hazırlığı için Oracle 'ı temsil eder.</span><span class="sxs-lookup"><span data-stu-id="ffee0-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="ffee0-106">Oracle $O $ ' e giriş:</span><span class="sxs-lookup"><span data-stu-id="ffee0-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="ffee0-107">İstenen hisse durumu $ \ket{\psı} s $ ' i depolayacak kayıt \_ .</span><span class="sxs-lookup"><span data-stu-id="ffee0-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="ffee0-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ffee0-108">Remarks</span></span>

<span data-ttu-id="ffee0-109">$O {0} \tus= \ket{\psı} $ tarafından tanımlanan bu Oracle, {0} $ \ket{\psı} $ durumunu oluşturmak için hesaplama tabanlı durum $ \tus$ üzerinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="ffee0-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="ffee0-110">İlk parametre, $ \ket{\psı} $ ' nin qubit kayıt dizinidir.</span><span class="sxs-lookup"><span data-stu-id="ffee0-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>