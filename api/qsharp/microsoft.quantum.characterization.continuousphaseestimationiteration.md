---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851903"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="a2c9b-102">ContinuousPhaseEstimationIteration işlemi</span><span class="sxs-lookup"><span data-stu-id="a2c9b-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="a2c9b-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="a2c9b-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="a2c9b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2c9b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2c9b-105">Bir Unitary Oracle 'ın rastgele gerçek üslerinin kullanıldığı yinelemeli (sınıflı kontrollü) bir aşama tahmini algoritması için tek bir yineleme gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a2c9b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a2c9b-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="a2c9b-107">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="a2c9b-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="a2c9b-108">$U $, aşaması tahmin edilecek olan Unitary ve $t $, Oracle 'a verilen tamsayı gücü olduğu için, bir çift $t $ ve bir $U yazmaç üzerinde işlem gören işlem.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="a2c9b-109">zaman: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a2c9b-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a2c9b-110">Verilen Unitary Oracle 'ın kaç kez uygulanacağını.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="a2c9b-111">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a2c9b-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a2c9b-112">Hedef durum üzerinde işlem yapmadan önce denetim qubit üzerindeki aşamanın tersine çevirmek için kullanılacak açı.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="a2c9b-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a2c9b-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a2c9b-114">Verilen Unitary Oracle tarafından üzerinde işlem yapılan durum kaydı.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="a2c9b-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a2c9b-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="a2c9b-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2c9b-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

