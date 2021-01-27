---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 005d7862214abb3dcb9c0caa006343720d179a52
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854477"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="e40e9-102">StateOracle Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="e40e9-102">StateOracle user defined type</span></span>

<span data-ttu-id="e40e9-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="e40e9-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="e40e9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e40e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e40e9-105">Durum hazırlığı için bir Oracle temsil eder.</span><span class="sxs-lookup"><span data-stu-id="e40e9-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="e40e9-106">Oracle $O $ girdileri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="e40e9-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="e40e9-107">Qubit $f $ bayrağını dizinleyen bir tamsayı.</span><span class="sxs-lookup"><span data-stu-id="e40e9-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="e40e9-108">System Register $s $, istenen hisse durumu $ \ket{\psı} s $ ' i depolayacak \_ .</span><span class="sxs-lookup"><span data-stu-id="e40e9-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="e40e9-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e40e9-109">Remarks</span></span>

<span data-ttu-id="e40e9-110">Bu Oracle tarafından tanımlanan bu Oracle $ $ O\ket {0} \_ {f} \ayraç {0} \_ s = \lambda\tusf\ket {1} \_ {\ PSI} \_ s + \sqrt{1-| \lambda | ^ 2} \demet {0} \_ f\cnoktalar, $ $ $ {0} \_ {0} \_ \tusf $ tarafından işaretlenen esasına göre $ \ket{\psı} s $ hedef durumu $ \_ \lambda $, genlik $ \lambda $ oluşturmak için hesaplama {1} tabanlı durum $ \tus{f} \tuss $ üzerinde çalışır \_ .</span><span class="sxs-lookup"><span data-stu-id="e40e9-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="e40e9-111">İlk parametre, $ \ket f $ ' nin qubit kaydına yönelik bir dizindir {0} \_ .</span><span class="sxs-lookup"><span data-stu-id="e40e9-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="e40e9-112">İkinci parametrenin her ikisi de kaydettirir.</span><span class="sxs-lookup"><span data-stu-id="e40e9-112">The second parameter encompassed both registers.</span></span>