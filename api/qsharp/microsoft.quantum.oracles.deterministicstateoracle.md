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
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="3258c-102">DeterministicStateOracle Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="3258c-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="3258c-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="3258c-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="3258c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3258c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3258c-105">Belirleyici bir durum hazırlığı için Oracle 'ı temsil eder.</span><span class="sxs-lookup"><span data-stu-id="3258c-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="3258c-106">Oracle $O $ ' e giriş:</span><span class="sxs-lookup"><span data-stu-id="3258c-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="3258c-107">İstenen hisse durumu $ \ket{\psı} s $ ' i depolayacak kayıt \_ .</span><span class="sxs-lookup"><span data-stu-id="3258c-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="3258c-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3258c-108">Remarks</span></span>

<span data-ttu-id="3258c-109">$O {0} \tus= \ket{\psı} $ tarafından tanımlanan bu Oracle, {0} $ \ket{\psı} $ durumunu oluşturmak için hesaplama tabanlı durum $ \tus$ üzerinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="3258c-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="3258c-110">İlk parametre, $ \ket{\psı} $ ' nin qubit kayıt dizinidir.</span><span class="sxs-lookup"><span data-stu-id="3258c-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>