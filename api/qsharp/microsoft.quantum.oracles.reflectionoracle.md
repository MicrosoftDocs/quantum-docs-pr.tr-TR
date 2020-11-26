---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226664"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="ca5e9-102">ReflectionOracle Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="ca5e9-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="ca5e9-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="ca5e9-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="ca5e9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca5e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca5e9-105">Bir yansımayı bir Oracle temsil eder.</span><span class="sxs-lookup"><span data-stu-id="ca5e9-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="ca5e9-106">Bir yansıma Oracle, $O $, girdileri vardır:</span><span class="sxs-lookup"><span data-stu-id="ca5e9-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="ca5e9-107">Yansıtılan alt alanın döndürüleceği $ \phi $ aşaması.</span><span class="sxs-lookup"><span data-stu-id="ca5e9-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="ca5e9-108">Verilen yansımanın gerçekleştirileceği qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="ca5e9-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="ca5e9-109">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="ca5e9-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a><span data-ttu-id="ca5e9-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="ca5e9-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="ca5e9-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ca5e9-111">Remarks</span></span>

<span data-ttu-id="ca5e9-112">Bu Oracle $O = \ cıvabitti-(1-e ^ {i \ Phi}) \ket{\psi}\bra{\psi} $, tek bir saf durum $ \ket{\psı} $ hakkında bir aşama $ \phi $ ile kısmi bir yansıma gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="ca5e9-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>