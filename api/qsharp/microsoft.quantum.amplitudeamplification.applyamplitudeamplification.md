---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: Applyamplitudeampsleştirme işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: be884eab70c7f72f994baf6bd7caf05769e0d5f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732034"
---
# <a name="applyamplitudeamplification-operation"></a><span data-ttu-id="92e31-102">Applyamplitudeampsleştirme işlemi</span><span class="sxs-lookup"><span data-stu-id="92e31-102">ApplyAmplitudeAmplification operation</span></span>

<span data-ttu-id="92e31-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="92e31-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="92e31-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="92e31-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="92e31-105">İlk ve son durumları yansıtmak için belirli bir aşamalar ve Oracles kümesini kullanarak belirli bir kayıt üzerinde genliği yükseltme uygular.</span><span class="sxs-lookup"><span data-stu-id="92e31-105">Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.</span></span>

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="92e31-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="92e31-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="92e31-107">Aşamalar: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="92e31-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="92e31-108">Genliği yükseltme algoritmasının her adımında kısmi yansımaları açıklayan bir aşamalar kümesi.</span><span class="sxs-lookup"><span data-stu-id="92e31-108">A set of phases describing the partial reflections at each step of the amplitude amplification algorithm.</span></span> <span data-ttu-id="92e31-109">@"microsoft.quantum.amplitudeamplification.standardreflectionphases"Bir örnek için bkz..</span><span class="sxs-lookup"><span data-stu-id="92e31-109">See @"microsoft.quantum.amplitudeamplification.standardreflectionphases" for an example.</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="92e31-110">Startstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="92e31-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="92e31-111">İlk durumunu yansıtan bir Oracle.</span><span class="sxs-lookup"><span data-stu-id="92e31-111">An oracle that reflects about the initial state.</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="92e31-112">Targetstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="92e31-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="92e31-113">İstenen son durumu gösteren bir Oracle.</span><span class="sxs-lookup"><span data-stu-id="92e31-113">An oracle that reflects about the desired final state.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="92e31-114">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="92e31-114">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="92e31-115">Üzerinde genliği yükseltme gerçekleştirmeye yönelik bir kayıt.</span><span class="sxs-lookup"><span data-stu-id="92e31-115">A register to perform amplitude amplification on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="92e31-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="92e31-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

