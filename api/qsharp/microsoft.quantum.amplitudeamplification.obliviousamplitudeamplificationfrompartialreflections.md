---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromPartialReflections
title: ObliviousAmplitudeAmplificationFromPartialReflections işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromPartialReflections
qsharp.summary: Returns a unitary that implements oblivious amplitude amplification by specifying for partial reflections.
ms.openlocfilehash: c818fcd8d8b83d8b479b4f133497449d500ca70e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191321"
---
# <a name="obliviousamplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="ddf6f-102">ObliviousAmplitudeAmplificationFromPartialReflections işlevi</span><span class="sxs-lookup"><span data-stu-id="ddf6f-102">ObliviousAmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="ddf6f-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="ddf6f-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="ddf6f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ddf6f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ddf6f-105">Kısmi yansıtımları için belirterek, yükümlülüğü uygulayan gensliği gerçekleştiren bir Unitary döndürür.</span><span class="sxs-lookup"><span data-stu-id="ddf6f-105">Returns a unitary that implements oblivious amplitude amplification by specifying for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="ddf6f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ddf6f-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="ddf6f-107">Aşamalar: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="ddf6f-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="ddf6f-108">Startstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="ddf6f-108">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="ddf6f-109">Targetstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="ddf6f-109">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="ddf6f-110">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="ddf6f-110">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>





## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="ddf6f-111">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="ddf6f-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

