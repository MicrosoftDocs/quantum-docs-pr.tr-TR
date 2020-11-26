---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6b2cf09c23942a586414daccb99cbb27b5026b9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226613"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="4d7e3-102">StateOracle Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="4d7e3-102">StateOracle user defined type</span></span>

<span data-ttu-id="4d7e3-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="4d7e3-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="4d7e3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d7e3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d7e3-105">Durum hazırlığı için bir Oracle temsil eder.</span><span class="sxs-lookup"><span data-stu-id="4d7e3-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="4d7e3-106">Oracle $O $ girdileri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="4d7e3-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="4d7e3-107">Qubit $f $ bayrağını dizinleyen bir tamsayı.</span><span class="sxs-lookup"><span data-stu-id="4d7e3-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="4d7e3-108">System Register $s $, istenen hisse durumu $ \ket{\psı} s $ ' i depolayacak \_ .</span><span class="sxs-lookup"><span data-stu-id="4d7e3-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="4d7e3-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4d7e3-109">Remarks</span></span>

<span data-ttu-id="4d7e3-110">Bu Oracle tarafından tanımlanan bu Oracle $ $ O\ket {0} \_ {f} \ayraç {0} \_ s = \lambda\tusf\ket {1} \_ {\ PSI} \_ s + \sqrt{1-| \lambda | ^ 2} \demet {0} \_ f\cnoktalar, $ $ $ {0} \_ {0} \_ \tusf $ tarafından işaretlenen esasına göre $ \ket{\psı} s $ hedef durumu $ \_ \lambda $, genlik $ \lambda $ oluşturmak için hesaplama {1} tabanlı durum $ \tus{f} \tuss $ üzerinde çalışır \_ .</span><span class="sxs-lookup"><span data-stu-id="4d7e3-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="4d7e3-111">İlk parametre, $ \ket f $ ' nin qubit kaydına yönelik bir dizindir {0} \_ .</span><span class="sxs-lookup"><span data-stu-id="4d7e3-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="4d7e3-112">İkinci parametrenin her ikisi de kaydettirir.</span><span class="sxs-lookup"><span data-stu-id="4d7e3-112">The second parameter encompassed both registers.</span></span>