---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: Yükseltilmiş Tudeamplificationfromstatehazırlama işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 7725ff327e327578ff36242a2b1bc6d03fab0d0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732042"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="53930-102">Yükseltilmiş Tudeamplificationfromstatehazırlama işlevi</span><span class="sxs-lookup"><span data-stu-id="53930-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="53930-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="53930-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="53930-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53930-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53930-105">Kısmi yansıtımları için Oracles tarafından bir aşağı yönlü yükseltme.</span><span class="sxs-lookup"><span data-stu-id="53930-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="53930-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="53930-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="53930-107">Aşamalar: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="53930-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="53930-108">Kısmi yansıtımları aşamaları</span><span class="sxs-lookup"><span data-stu-id="53930-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="53930-109">stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="53930-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="53930-110">Başlangıç durumunu hazırlayan Unitary Oracle $A $</span><span class="sxs-lookup"><span data-stu-id="53930-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="53930-111">ıdxflagqubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53930-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53930-112">Bayrak qubit 'e kadar Dizin</span><span class="sxs-lookup"><span data-stu-id="53930-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="53930-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="53930-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="53930-114">Kısmi yansıtımları tarafından uygulanan Oracles tarafından kullanılan genliği uygulayan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="53930-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="53930-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="53930-115">Remarks</span></span>

<span data-ttu-id="53930-116">Bu, başlangıç ve hedef durumlarının biçiminde öğesinden daha sıkı koşullar uygular `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="53930-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="53930-117">Hedef durumun $ \ket f $ tarafından işaretlenmiş olduğu varsayılır {1} \_ .</span><span class="sxs-lookup"><span data-stu-id="53930-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="53930-118">\Begin{hizalaması} A\ket {0} \_ {f} \demet {0} \_ s = \lambda\tusf\ket {1} \_ {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} {0} \_ \tusf\cnoktalar, \end{hizalaması} çoğu durumda `flagQubit` ve `auxiliaryRegister` $ \demet {0} \_ {f} \ demet {0} \_ s $ durumunda başlatılır.</span><span class="sxs-lookup"><span data-stu-id="53930-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>