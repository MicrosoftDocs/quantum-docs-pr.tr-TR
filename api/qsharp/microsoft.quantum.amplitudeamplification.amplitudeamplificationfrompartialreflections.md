---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: Amptudeamplificationfrompartialyansıtıctions işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: e4030aabcab55db35bcb8199e37bee837ead6ad0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845914"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="6727a-102">Amptudeamplificationfrompartialyansıtıctions işlevi</span><span class="sxs-lookup"><span data-stu-id="6727a-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="6727a-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="6727a-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="6727a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6727a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6727a-105">Kısmi yansıtımları ile genliği yükseltme.</span><span class="sxs-lookup"><span data-stu-id="6727a-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="6727a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6727a-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="6727a-107">Aşamalar: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="6727a-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="6727a-108">Kısmi yansıtımları aşamaları</span><span class="sxs-lookup"><span data-stu-id="6727a-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="6727a-109">Startstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="6727a-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="6727a-110">Başlangıç durumu hakkında yansıma işleci</span><span class="sxs-lookup"><span data-stu-id="6727a-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="6727a-111">Targetstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="6727a-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="6727a-112">Hedef durumu hakkında yansıma işleci</span><span class="sxs-lookup"><span data-stu-id="6727a-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="6727a-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="6727a-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6727a-114">Kısmi yansıtımları tarafından genliği uygulayan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="6727a-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="6727a-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6727a-115">Remarks</span></span>

<span data-ttu-id="6727a-116">Genlik yükseltme, hiçbir sistem qubit olmadığı ve yükümlülüğü olarak Oracle 'ın kimlik olarak ayarlandığı, yükümlülüğü bir genlik genkezliği olan özel bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="6727a-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="6727a-117">Çoğu durumda, $ `startQubits` \_ -$1 eigenstate olan $ \ket{\Text{Start}} $1 durumunda başlatılır `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="6727a-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>