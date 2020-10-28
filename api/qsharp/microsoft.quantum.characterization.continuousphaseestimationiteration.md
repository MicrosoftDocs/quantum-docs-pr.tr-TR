---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: a3914a4b19e3b898b6de8808699da09d386f487a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728232"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="90ec6-102">ContinuousPhaseEstimationIteration işlemi</span><span class="sxs-lookup"><span data-stu-id="90ec6-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="90ec6-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="90ec6-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="90ec6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="90ec6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="90ec6-105">Bir Unitary Oracle 'ın rastgele gerçek üslerinin kullanıldığı yinelemeli (sınıflı kontrollü) bir aşama tahmini algoritması için tek bir yineleme gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="90ec6-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="90ec6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="90ec6-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="90ec6-107">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="90ec6-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="90ec6-108">$U $, aşaması tahmin edilecek olan Unitary ve $t $, Oracle 'a verilen tamsayı gücü olduğu için, bir çift $t $ ve bir $U yazmaç üzerinde işlem gören işlem.</span><span class="sxs-lookup"><span data-stu-id="90ec6-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="90ec6-109">zaman: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="90ec6-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="90ec6-110">Verilen Unitary Oracle 'ın kaç kez uygulanacağını.</span><span class="sxs-lookup"><span data-stu-id="90ec6-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="90ec6-111">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="90ec6-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="90ec6-112">Hedef durum üzerinde işlem yapmadan önce denetim qubit üzerindeki aşamanın tersine çevirmek için kullanılacak açı.</span><span class="sxs-lookup"><span data-stu-id="90ec6-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="90ec6-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="90ec6-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="90ec6-114">Verilen Unitary Oracle tarafından üzerinde işlem yapılan durum kaydı.</span><span class="sxs-lookup"><span data-stu-id="90ec6-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="90ec6-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="90ec6-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="90ec6-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90ec6-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

