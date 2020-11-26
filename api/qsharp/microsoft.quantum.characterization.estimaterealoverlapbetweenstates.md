---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: EstimateRealOverlapBetweenStates işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: d9f569ceffc16f377189dc94035213b9075609cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216192"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a><span data-ttu-id="0eeee-102">EstimateRealOverlapBetweenStates işlemi</span><span class="sxs-lookup"><span data-stu-id="0eeee-102">EstimateRealOverlapBetweenStates operation</span></span>

<span data-ttu-id="0eeee-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="0eeee-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="0eeee-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0eeee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0eeee-105">Her birinin bir durum kopyasını hazırlayabileceği iki işlem, her bir işlem tarafından hazırlanan durumlar arasındaki örtüşme işleminin gerçek parçasını tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="0eeee-105">Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="0eeee-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0eeee-106">Input</span></span>

### <a name="commonpreparation--qubit--unit--is-adj"></a><span data-ttu-id="0eeee-107">Commonhazırlama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="0eeee-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0eeee-108">Sabit bir giriş durumunu hazırlayan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="0eeee-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit--is-adj--ctl"></a><span data-ttu-id="0eeee-109">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="0eeee-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="0eeee-110">Karşılaştırılacak iki durum hazırlık işlemi.</span><span class="sxs-lookup"><span data-stu-id="0eeee-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj--ctl"></a><span data-ttu-id="0eeee-111">preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="0eeee-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="0eeee-112">Karşılaştırılacak iki durum hazırlık işlemi saniyesi.</span><span class="sxs-lookup"><span data-stu-id="0eeee-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="0eeee-113">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0eeee-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0eeee-114">`commonPreparation`, `preparation1` Ve hepsi üzerinde işlem gören qubit sayısı `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="0eeee-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="0eeee-115">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0eeee-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0eeee-116">Örtüşmeyi tahmin etmek için kullanılacak ölçüm sayısı.</span><span class="sxs-lookup"><span data-stu-id="0eeee-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="0eeee-117">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0eeee-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="0eeee-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0eeee-118">Remarks</span></span>

<span data-ttu-id="0eeee-119">Bu işlem, $ $ \begin{hizalaması} \braket{\psı | öğesinin gerçek parçasını bulmak için Hadamard testini kullanır V ^ {\ dağılım} U | \psı} \end{hizalaması} $ $; $ \ket{\psı} $, tarafından hazırlanan durumdur `commonPreparation` , $U $, ' nin eyleminin Unitary gösterimidir `preparation1` ve $V $ öğesinin karşılık geldiği yerdir `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="0eeee-119">This operation uses the Hadamard test to find the real part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="0eeee-120">Başvurular</span><span class="sxs-lookup"><span data-stu-id="0eeee-120">References</span></span>

- <span data-ttu-id="0eeee-121">Aharonov *et al.* [Quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="0eeee-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="0eeee-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0eeee-122">See Also</span></span>

- [<span data-ttu-id="0eeee-123">Microsoft. hisse. karakterleştirme. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="0eeee-123">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [<span data-ttu-id="0eeee-124">Microsoft. hisse. karakterleştirme. EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="0eeee-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)