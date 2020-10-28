---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: Standarsönlitudeamplifleştirme işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 18228d45c4df280b004c595a7b0f1e2a607b8b2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731930"
---
# <a name="standardamplitudeamplification-function"></a><span data-ttu-id="092cd-102">Standarsönlitudeamplifleştirme işlevi</span><span class="sxs-lookup"><span data-stu-id="092cd-102">StandardAmplitudeAmplification function</span></span>

<span data-ttu-id="092cd-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="092cd-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="092cd-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="092cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="092cd-105">Standart genliği yükseltme algoritması</span><span class="sxs-lookup"><span data-stu-id="092cd-105">Standard Amplitude Amplification algorithm</span></span>

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="092cd-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="092cd-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="092cd-107">Nyinelemeler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="092cd-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="092cd-108">Genliği yükseltme $n yineleme sayısı</span><span class="sxs-lookup"><span data-stu-id="092cd-108">Number of iterations $n$ of amplitude amplification</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="092cd-109">stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="092cd-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="092cd-110">Başlangıç durumunu hazırlayan Unitary Oracle $A $</span><span class="sxs-lookup"><span data-stu-id="092cd-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="092cd-111">ıdxflagqubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="092cd-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="092cd-112">Bayrak qubit 'e kadar Dizin</span><span class="sxs-lookup"><span data-stu-id="092cd-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="092cd-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="092cd-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="092cd-114">Standart genliği yükseltme hisse algoritması algoritmasını uygulayan bir işlem</span><span class="sxs-lookup"><span data-stu-id="092cd-114">An operation that implements the standard amplitude amplification quantum algorithm</span></span>

## <a name="remarks"></a><span data-ttu-id="092cd-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="092cd-115">Remarks</span></span>

<span data-ttu-id="092cd-116">Bu, `AmpAmpPhasesStandard` \begin{hizalaması} A\ket {0} \_ {f} {0} \_ \gens = \lambda\tusf\ket {1} \_ {\ Text {Target}} \_ + \ sqrt{1-| \lambda | ^ 2} {0} \_ \tusf\cnoktalar, \end{hizalaması} bu işlem, çoğu durumda \begin{hizalaması} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} {0} \_ \tuss = \sin ((2n + 1) \sin ^ {-1} (\lambda)) {1} \_ \tusf\ket {\ Text {Target}} \_ s + \cdots\tusf {0} \_ \end{hizalaması} durumunu hazırlar. `flagQubit` ve `auxiliaryRegister` $ \demet {0} \_ f\tusa $ ' da başlatılır {0} \_ .</span><span class="sxs-lookup"><span data-stu-id="092cd-116">This is the standard amplitude amplification algorithm obtained by a choice of reflection phases computed by `AmpAmpPhasesStandard` Assuming that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} this operation prepares the state \begin{align} \operatorname{AmpAmpByOracle}\ket{0}\_{f}\ket{0}\_s= \sin((2n+1)\sin^{-1}(\lambda))\ket{1}\_f\ket{\text{target}}\_s + \cdots\ket{0}\_f \end{align} In most cases, `flagQubit` and `auxiliaryRegister` is initialized in the state $\ket{0}\_f\ket{0}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="092cd-117">Referanslar</span><span class="sxs-lookup"><span data-stu-id="092cd-117">References</span></span>

- [<span data-ttu-id="092cd-118">*G. Brassard, P. Hoyer, M. Mosca, a. Tapp*</span><span class="sxs-lookup"><span data-stu-id="092cd-118"> *G. Brassard, P. Hoyer, M. Mosca, A. Tapp* </span></span>](https://arxiv.org/abs/quant-ph/0005055)