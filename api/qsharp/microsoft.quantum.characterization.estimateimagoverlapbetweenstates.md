---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: EstimateImagOverlapBetweenStates işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 8b73115c3243c594897ac4b309ec52d5e9863d26
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728219"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a><span data-ttu-id="eb254-102">EstimateImagOverlapBetweenStates işlemi</span><span class="sxs-lookup"><span data-stu-id="eb254-102">EstimateImagOverlapBetweenStates operation</span></span>

<span data-ttu-id="eb254-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="eb254-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="eb254-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb254-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb254-105">Her birinin bir durum kopyasını hazırlayabileceği iki işlem, her bir işlem tarafından hazırlanan durumlar arasındaki çakışmadan oluşan sanal kısmını tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="eb254-105">Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="eb254-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="eb254-106">Input</span></span>

### <a name="commonpreparation--qubit--unit-adj"></a><span data-ttu-id="eb254-107">Commonhazırlama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="eb254-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="eb254-108">Sabit bir giriş durumunu hazırlayan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="eb254-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit-adj--ctl"></a><span data-ttu-id="eb254-109">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="eb254-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="eb254-110">Karşılaştırılacak iki durum hazırlık işlemi.</span><span class="sxs-lookup"><span data-stu-id="eb254-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj--ctl"></a><span data-ttu-id="eb254-111">preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="eb254-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="eb254-112">Karşılaştırılacak iki durum hazırlık işlemi saniyesi.</span><span class="sxs-lookup"><span data-stu-id="eb254-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="eb254-113">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eb254-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eb254-114">`commonPreparation`, `preparation1` Ve hepsi üzerinde işlem gören qubit sayısı `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="eb254-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="eb254-115">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eb254-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eb254-116">Örtüşmeyi tahmin etmek için kullanılacak ölçüm sayısı.</span><span class="sxs-lookup"><span data-stu-id="eb254-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="eb254-117">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eb254-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="eb254-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="eb254-118">Remarks</span></span>

<span data-ttu-id="eb254-119">Bu işlem, $ $ \begin{hizalaması} \braket{\psı | öğesinin sanal bölümünü bulmak için Hadamard testini kullanır V ^ {\ dağılım} U | \psı} \end{hizalaması} $ $; $ \ket{\psı} $, tarafından hazırlanan durumdur `commonPreparation` , $U $, ' nin eyleminin Unitary gösterimidir `preparation1` ve $V $ öğesinin karşılık geldiği yerdir `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="eb254-119">This operation uses the Hadamard test to find the imaginary part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="eb254-120">Referanslar</span><span class="sxs-lookup"><span data-stu-id="eb254-120">References</span></span>

- <span data-ttu-id="eb254-121">Aharonov *et al.* [Quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="eb254-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="eb254-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="eb254-122">See Also</span></span>

- [<span data-ttu-id="eb254-123">Microsoft. hisse. karakterleştirme. EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="eb254-123">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="eb254-124">Microsoft. hisse. karakterleştirme. EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="eb254-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)