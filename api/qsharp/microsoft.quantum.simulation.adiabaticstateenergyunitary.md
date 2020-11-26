---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: AdiabaticStateEnergyUnitary işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: a69eb29318a750bea9c7c84ae4f90f7a31007c33
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225542"
---
# <a name="adiabaticstateenergyunitary-operation"></a><span data-ttu-id="bb1a2-102">AdiabaticStateEnergyUnitary işlemi</span><span class="sxs-lookup"><span data-stu-id="bb1a2-102">AdiabaticStateEnergyUnitary operation</span></span>

<span data-ttu-id="bb1a2-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bb1a2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bb1a2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bb1a2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bb1a2-105">Giriş durumuna uygulayarak durum hazırlama işlemini gerçekleştirir ve sonuç olarak bir ile bir `statePrepUnitary` `adiabaticUnitary` , son aşama tahmini kullanarak, bir, ve son derece tahmini kullanarak bir, ve son aşama tahmini kullanın `qpeUnitary` `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="bb1a2-105">Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="bb1a2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="bb1a2-106">Input</span></span>

### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="bb1a2-107">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bb1a2-107">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bb1a2-108">İlk dinamik oluşturucusunun durum hazırlanmasını temsil eden bir Oracle.</span><span class="sxs-lookup"><span data-stu-id="bb1a2-108">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="bb1a2-109">adiabaticUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bb1a2-109">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bb1a2-110">En iyi EPS 'yi algoritmanın son durumuna uygulamak için kullanılacak Adiabatik evsel algoritmayı temsil eden bir Oracle.</span><span class="sxs-lookup"><span data-stu-id="bb1a2-110">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="bb1a2-111">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="bb1a2-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bb1a2-112">Bir Unitary işlecini temsil eden bir Oracle $U $ \ma{\phi} $ ve taban durumu enerji $E = \fi \\ , \ Delta t $ ile bir dinamik üreticisi altında</span><span class="sxs-lookup"><span data-stu-id="bb1a2-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="bb1a2-113">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bb1a2-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="bb1a2-114">Belirli bir Unitary işleminde aşama tahmini gerçekleştiren bir işlem.</span><span class="sxs-lookup"><span data-stu-id="bb1a2-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="bb1a2-115">Daha fazla ayrıntı için bkz. [yinelemeli aşama tahmini](/quantum/libraries/characterization#iterative-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="bb1a2-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="bb1a2-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bb1a2-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bb1a2-117">Simülasyonu gerçekleştirmek için kullanılacak qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="bb1a2-117">A register of qubits to be used to perform the simulation.</span></span>



## <a name="output--double"></a><span data-ttu-id="bb1a2-118">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bb1a2-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bb1a2-119">$U $ tarafından temsil edilen oluşturucunun zemin devlet enerji $ \phi $ tahmini $ \hat{\phi} $.</span><span class="sxs-lookup"><span data-stu-id="bb1a2-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>