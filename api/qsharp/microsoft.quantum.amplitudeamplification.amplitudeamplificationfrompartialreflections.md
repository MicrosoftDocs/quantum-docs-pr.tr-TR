---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: Amptudeamplificationfrompartialyansıtıctions işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: 8fa6db7d5616f8c561191e3da00a69b05041b279
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191695"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="a37d9-102">Amptudeamplificationfrompartialyansıtıctions işlevi</span><span class="sxs-lookup"><span data-stu-id="a37d9-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="a37d9-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="a37d9-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="a37d9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a37d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a37d9-105">Kısmi yansıtımları ile genliği yükseltme.</span><span class="sxs-lookup"><span data-stu-id="a37d9-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="a37d9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a37d9-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="a37d9-107">Aşamalar: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="a37d9-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="a37d9-108">Kısmi yansıtımları aşamaları</span><span class="sxs-lookup"><span data-stu-id="a37d9-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="a37d9-109">Startstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="a37d9-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="a37d9-110">Başlangıç durumu hakkında yansıma işleci</span><span class="sxs-lookup"><span data-stu-id="a37d9-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="a37d9-111">Targetstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="a37d9-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="a37d9-112">Hedef durumu hakkında yansıma işleci</span><span class="sxs-lookup"><span data-stu-id="a37d9-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="a37d9-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="a37d9-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a37d9-114">Kısmi yansıtımları tarafından genliği uygulayan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="a37d9-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="a37d9-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a37d9-115">Remarks</span></span>

<span data-ttu-id="a37d9-116">Genlik yükseltme, hiçbir sistem qubit olmadığı ve yükümlülüğü olarak Oracle 'ın kimlik olarak ayarlandığı, yükümlülüğü bir genlik genkezliği olan özel bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="a37d9-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="a37d9-117">Çoğu durumda, $ `startQubits` \_ -$1 eigenstate olan $ \ket{\Text{Start}} $1 durumunda başlatılır `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="a37d9-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>