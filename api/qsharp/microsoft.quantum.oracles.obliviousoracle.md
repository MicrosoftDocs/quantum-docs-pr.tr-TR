---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 7c5b35984f3c8828a5ba9bdae8f9effbc1d378f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726480"
---
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="69ef9-102">ObliviousOracle Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="69ef9-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="69ef9-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="69ef9-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="69ef9-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69ef9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69ef9-105">Bir Oracle 'ın yükümlülüğü en çok genliğini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="69ef9-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="69ef9-106">Oracle $O $ girdileri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="69ef9-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="69ef9-107">Anyükleyen La, $O $ 'ın üzerinde davranması $a $.</span><span class="sxs-lookup"><span data-stu-id="69ef9-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="69ef9-108">İstenen Unitary $U $ ' in uygulandığı $s $, kayıt sonrasında $ \ket{t} a $ konumundaki $a $ konumunda seçili olan sistem kaydı \_ .</span><span class="sxs-lookup"><span data-stu-id="69ef9-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="69ef9-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="69ef9-109">Remarks</span></span>

<span data-ttu-id="69ef9-110">Bu Oracle tarafından tanımlanan bu Oracle $ $ O\ket {s} \_ a\ket {\ PSI} \_ s = \lambda\ket{t} \_ a U \ket{\psı} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cnoktalara $ $, $ \_ \ket{t} a $ tarafından işaretlenen temelinde her türlü sistem durumu $ \ket{\psi} \_ s $, genlik $ \lambda $ olan herhangi bir sistem durumunda Unitary $U $ ' i uygulamak için ansınla State $ \ket{s} a $ üzerinde çalışır \_ .</span><span class="sxs-lookup"><span data-stu-id="69ef9-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="69ef9-111">İlk parametre $ \ket{s} a $ 'ın qubit kayıt dizinidir \_ .</span><span class="sxs-lookup"><span data-stu-id="69ef9-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="69ef9-112">İkinci parametre, $ \ket{\psı} s $ ' nin qubit kayıt dizinidir \_ .</span><span class="sxs-lookup"><span data-stu-id="69ef9-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>