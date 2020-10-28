---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: Estimateenerji işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: ba4a5372aaf092c3ac3a1302f9715ca643be8436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732106"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="07c84-102">Estimateenerji işlemi</span><span class="sxs-lookup"><span data-stu-id="07c84-102">EstimateEnergy operation</span></span>

<span data-ttu-id="07c84-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="07c84-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="07c84-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07c84-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07c84-105">`statePrepUnitary`, `qpeUnitary` İle elde edilen duruma göre otomatik olarak ayrılmış bir giriş durumu aşaması tahmini temelinde bir durum hazırlığı gerçekleştirir `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="07c84-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="07c84-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="07c84-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="07c84-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="07c84-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="07c84-108">Simülasyonu gerçekleştirmek için kullanılan qubits sayısı.</span><span class="sxs-lookup"><span data-stu-id="07c84-108">Number of qubits used to perform simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="07c84-109">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07c84-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="07c84-110">İlk dinamik oluşturucusunun durum hazırlanmasını temsil eden bir Oracle.</span><span class="sxs-lookup"><span data-stu-id="07c84-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="qpeunitary--qubit--unit-adj--ctl"></a><span data-ttu-id="07c84-111">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="07c84-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="07c84-112">Bir Unitary işlecini temsil eden bir Oracle $U $ \ma{\phi} $ ve taban durumu enerji $E = \fi \\ , \ Delta t $ ile bir dinamik üreticisi altında</span><span class="sxs-lookup"><span data-stu-id="07c84-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="07c84-113">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="07c84-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="07c84-114">Belirli bir Unitary işleminde aşama tahmini gerçekleştiren bir işlem.</span><span class="sxs-lookup"><span data-stu-id="07c84-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="07c84-115">Daha fazla ayrıntı için bkz. [yinelemeli aşama tahmini](/quantum/libraries/characterization#iterative-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="07c84-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="07c84-116">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="07c84-116">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="07c84-117">$U $ tarafından temsil edilen oluşturucunun zemin devlet enerjisi 'nin zemin devlet enerji $ \phi $ \hat{\phi} $.</span><span class="sxs-lookup"><span data-stu-id="07c84-117">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the ground state energy of the generator represented by $U$.</span></span>