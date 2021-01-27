---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimateOverlapBetweenStates işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: e083d6da13b0780905bf365c7a428ebc9666ce9e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839710"
---
# <a name="estimateoverlapbetweenstates-operation"></a><span data-ttu-id="748ca-102">EstimateOverlapBetweenStates işlemi</span><span class="sxs-lookup"><span data-stu-id="748ca-102">EstimateOverlapBetweenStates operation</span></span>

<span data-ttu-id="748ca-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="748ca-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="748ca-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="748ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="748ca-105">Her birinin bir durum kopyasını hazırlayabileceği iki işlem, her bir işlem tarafından hazırlanan durumlar arasındaki kare Örtüşmeyi tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="748ca-105">Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="748ca-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="748ca-106">Input</span></span>

### <a name="preparation1--qubit--unit--is-adj"></a><span data-ttu-id="748ca-107">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="748ca-107">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="748ca-108">Karşılaştırılacak iki durum hazırlık işlemi.</span><span class="sxs-lookup"><span data-stu-id="748ca-108">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj"></a><span data-ttu-id="748ca-109">preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="748ca-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="748ca-110">Karşılaştırılacak iki durum hazırlık işlemi saniyesi.</span><span class="sxs-lookup"><span data-stu-id="748ca-110">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="748ca-111">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="748ca-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="748ca-112">`commonPreparation`, `preparation1` Ve hepsi üzerinde işlem gören qubit sayısı `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="748ca-112">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="748ca-113">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="748ca-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="748ca-114">Örtüşmeyi tahmin etmek için kullanılacak ölçüm sayısı.</span><span class="sxs-lookup"><span data-stu-id="748ca-114">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="748ca-115">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="748ca-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="748ca-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="748ca-116">Remarks</span></span>

<span data-ttu-id="748ca-117">Bu işlem, $ $ \begin{hizalaması} \left | bulmak için takas testini kullanır | \braket{00\cnoktalar 0 | V ^ {\ dağılım} U | 00 \ cnoktalar 0} \ Right | ^ 2 \end{hizalaması} $ $; burada $U $, eyleminin işlem için Unitary gösterimidir `preparation1` ve $V $ öğesinin karşılık geldiği yerdir `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="748ca-117">This operation uses the SWAP test to find $$ \begin{align} \left| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \right|^2 \end{align} $$ where $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="see-also"></a><span data-ttu-id="748ca-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="748ca-118">See Also</span></span>

- [<span data-ttu-id="748ca-119">Microsoft. hisse. karakterleştirme. EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="748ca-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="748ca-120">Microsoft. hisse. karakterleştirme. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="748ca-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)