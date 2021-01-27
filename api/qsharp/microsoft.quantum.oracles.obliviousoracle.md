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
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="317b7-102">ObliviousOracle Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="317b7-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="317b7-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="317b7-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="317b7-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="317b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="317b7-105">Bir Oracle 'ın yükümlülüğü en çok genliğini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="317b7-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="317b7-106">Oracle $O $ girdileri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="317b7-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="317b7-107">Anyükleyen La, $O $ 'ın üzerinde davranması $a $.</span><span class="sxs-lookup"><span data-stu-id="317b7-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="317b7-108">İstenen Unitary $U $ ' in uygulandığı $s $, kayıt sonrasında $ \ket{t} a $ konumundaki $a $ konumunda seçili olan sistem kaydı \_ .</span><span class="sxs-lookup"><span data-stu-id="317b7-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="317b7-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="317b7-109">Remarks</span></span>

<span data-ttu-id="317b7-110">Bu Oracle tarafından tanımlanan bu Oracle $ $ O\ket {s} \_ a\ket {\ PSI} \_ s = \lambda\ket{t} \_ a U \ket{\psı} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cnoktalara $ $, $ \_ \ket{t} a $ tarafından işaretlenen temelinde her türlü sistem durumu $ \ket{\psi} \_ s $, genlik $ \lambda $ olan herhangi bir sistem durumunda Unitary $U $ ' i uygulamak için ansınla State $ \ket{s} a $ üzerinde çalışır \_ .</span><span class="sxs-lookup"><span data-stu-id="317b7-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="317b7-111">İlk parametre $ \ket{s} a $ 'ın qubit kayıt dizinidir \_ .</span><span class="sxs-lookup"><span data-stu-id="317b7-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="317b7-112">İkinci parametre, $ \ket{\psı} s $ ' nin qubit kayıt dizinidir \_ .</span><span class="sxs-lookup"><span data-stu-id="317b7-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>