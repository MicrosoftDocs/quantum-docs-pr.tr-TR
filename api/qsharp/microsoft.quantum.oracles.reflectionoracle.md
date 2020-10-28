---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733338"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="2e789-102">ReflectionOracle Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="2e789-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="2e789-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="2e789-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="2e789-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e789-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2e789-105">Bir yansımayı bir Oracle temsil eder.</span><span class="sxs-lookup"><span data-stu-id="2e789-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="2e789-106">Bir yansıma Oracle, $O $, girdileri vardır:</span><span class="sxs-lookup"><span data-stu-id="2e789-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="2e789-107">Yansıtılan alt alanın döndürüleceği $ \phi $ aşaması.</span><span class="sxs-lookup"><span data-stu-id="2e789-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="2e789-108">Verilen yansımanın gerçekleştirileceği qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="2e789-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="2e789-109">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="2e789-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a><span data-ttu-id="2e789-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="2e789-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="2e789-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2e789-111">Remarks</span></span>

<span data-ttu-id="2e789-112">Bu Oracle $O = \ cıvabitti-(1-e ^ {i \ Phi}) \ket{\psi}\bra{\psi} $, tek bir saf durum $ \ket{\psı} $ hakkında bir aşama $ \phi $ ile kısmi bir yansıma gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="2e789-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>