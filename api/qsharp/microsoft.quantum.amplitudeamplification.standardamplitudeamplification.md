---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: Standarsönlitudeamplifleştirme işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 984bfee89b6d79750228b8ca6aaf404f58aecd41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843939"
---
# <a name="standardamplitudeamplification-function"></a><span data-ttu-id="11a21-102">Standarsönlitudeamplifleştirme işlevi</span><span class="sxs-lookup"><span data-stu-id="11a21-102">StandardAmplitudeAmplification function</span></span>

<span data-ttu-id="11a21-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="11a21-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="11a21-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="11a21-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="11a21-105">Standart genliği yükseltme algoritması</span><span class="sxs-lookup"><span data-stu-id="11a21-105">Standard Amplitude Amplification algorithm</span></span>

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="11a21-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="11a21-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="11a21-107">Nyinelemeler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="11a21-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="11a21-108">Genliği yükseltme $n yineleme sayısı</span><span class="sxs-lookup"><span data-stu-id="11a21-108">Number of iterations $n$ of amplitude amplification</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="11a21-109">stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="11a21-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="11a21-110">Başlangıç durumunu hazırlayan Unitary Oracle $A $</span><span class="sxs-lookup"><span data-stu-id="11a21-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="11a21-111">ıdxflagqubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="11a21-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="11a21-112">Bayrak qubit 'e kadar Dizin</span><span class="sxs-lookup"><span data-stu-id="11a21-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="11a21-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="11a21-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="11a21-114">Standart genliği yükseltme hisse algoritması algoritmasını uygulayan bir işlem</span><span class="sxs-lookup"><span data-stu-id="11a21-114">An operation that implements the standard amplitude amplification quantum algorithm</span></span>

## <a name="remarks"></a><span data-ttu-id="11a21-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="11a21-115">Remarks</span></span>

<span data-ttu-id="11a21-116">Bu, `AmpAmpPhasesStandard` \begin{hizalaması} A\ket {0} \_ {f} {0} \_ \gens = \lambda\tusf\ket {1} \_ {\ Text {Target}} \_ + \ sqrt{1-| \lambda | ^ 2} {0} \_ \tusf\cnoktalar, \end{hizalaması} bu işlem, çoğu durumda \begin{hizalaması} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} {0} \_ \tuss = \sin ((2n + 1) \sin ^ {-1} (\lambda)) {1} \_ \tusf\ket {\ Text {Target}} \_ s + \cdots\tusf {0} \_ \end{hizalaması} durumunu hazırlar. `flagQubit` ve `auxiliaryRegister` $ \demet {0} \_ f\tusa $ ' da başlatılır {0} \_ .</span><span class="sxs-lookup"><span data-stu-id="11a21-116">This is the standard amplitude amplification algorithm obtained by a choice of reflection phases computed by `AmpAmpPhasesStandard` Assuming that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} this operation prepares the state \begin{align} \operatorname{AmpAmpByOracle}\ket{0}\_{f}\ket{0}\_s= \sin((2n+1)\sin^{-1}(\lambda))\ket{1}\_f\ket{\text{target}}\_s + \cdots\ket{0}\_f \end{align} In most cases, `flagQubit` and `auxiliaryRegister` is initialized in the state $\ket{0}\_f\ket{0}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="11a21-117">Başvurular</span><span class="sxs-lookup"><span data-stu-id="11a21-117">References</span></span>

- [<span data-ttu-id="11a21-118">*G. Brassard, P. Hoyer, M. Mosca, a. Tapp*</span><span class="sxs-lookup"><span data-stu-id="11a21-118"> *G. Brassard, P. Hoyer, M. Mosca, A. Tapp* </span></span>](https://arxiv.org/abs/quant-ph/0005055)