---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 873c436d4b8d8efc9dc61c2baba9b0e0f7f09fc2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845815"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="787d2-102">ObliviousAmplitudeAmplificationFromStatePreparation işlevi</span><span class="sxs-lookup"><span data-stu-id="787d2-102">ObliviousAmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="787d2-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="787d2-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="787d2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="787d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="787d2-105">Yükümlülüğü, kısmi yansıtımları için Oracles tarafından bir şekilde geliştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="787d2-105">Oblivious amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="787d2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="787d2-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="787d2-107">Aşamalar: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="787d2-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="787d2-108">Kısmi yansıtımları aşamaları</span><span class="sxs-lookup"><span data-stu-id="787d2-108">Phases of partial reflections</span></span>


### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="787d2-109">startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="787d2-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="787d2-110">Yardımcı başlangıç durumunu hazırlayan Unitary Oracle $A $</span><span class="sxs-lookup"><span data-stu-id="787d2-110">Unitary oracle $A$ that prepares auxiliary start state</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="787d2-111">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="787d2-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="787d2-112">Ortak `ObliviousOracle` ve sistem kaydı üzerinde birlikte çalışan türdeki Unitary oracle $O $</span><span class="sxs-lookup"><span data-stu-id="787d2-112">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system register</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="787d2-113">ıdxflagqubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="787d2-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="787d2-114">Tek qubit bayrak kaydına yönelik Dizin</span><span class="sxs-lookup"><span data-stu-id="787d2-114">Index to single-qubit flag register</span></span>



## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="787d2-115">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="787d2-115">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="787d2-116">Yükümlülüğü uygulayan, kısmi yansımaları temel alan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="787d2-116">An operation that implements oblivious amplitude amplification based on partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="787d2-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="787d2-117">Remarks</span></span>

<span data-ttu-id="787d2-118">Bu, yardımcı başlangıç ve hedef durumlarının biçimine kıyasla daha sıkı koşullar uygular `AmpAmpObliviousByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="787d2-118">This imposes stricter conditions on form of the auxiliary start and target states than in `AmpAmpObliviousByReflectionPhases`.</span></span>
<span data-ttu-id="787d2-119">$A {0} \_ \tusf\demet {0} \_ A = \ket{\Text{Start}} \_ {FA} $, yardımcı başlangıç durumunu $ \ket{\Text{Start}} \_ {FA} $ değerini hesaplama tabanlı $ {0} \_ \tusf\ket $ ' nden hazırlar {0} .</span><span class="sxs-lookup"><span data-stu-id="787d2-119">It is assumed that $A\ket{0}\_f\ket{0}\_a= \ket{\text{start}}\_{fa}$ prepares the auxiliary start state $\ket{\text{start}}\_{fa}$ from the computational basis $\ket{0}\_f\ket{0}$.</span></span>
<span data-ttu-id="787d2-120">Hedef durumun $ \ket f $ tarafından işaretlenmiş olduğu varsayılır {1} \_ .</span><span class="sxs-lookup"><span data-stu-id="787d2-120">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="787d2-121">\Begin{hizalaması} O\ket {\ Text {Start}} \_ {FA} \ket{\psı} \_ s = \lambdad\tusf\tus{ {1} \_ \ Text {bir}} \_ a\tus{\ Text {Target}} \_ s U \ket{\psı} \_ s + \sqrt{1-| \lambda | ^ 2} \tusf\cnoktalar {0} \_ , \end{hizalaması}, bazı Unitary $U $.</span><span class="sxs-lookup"><span data-stu-id="787d2-121">It is assumed that \begin{align} O\ket{\text{start}}\_{fa}\ket{\psi}\_s= \lambda\ket{1}\_f\ket{\text{anything}}\_a\ket{\text{target}}\_s U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} for some unitary $U$.</span></span>