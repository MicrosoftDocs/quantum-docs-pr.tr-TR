---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 8ce1e1a2bda6507285f055c87619a8760c891082
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204394"
---
# <a name="discretephaseestimationiteration-operation"></a><span data-ttu-id="73c73-102">DiscretePhaseEstimationIteration işlemi</span><span class="sxs-lookup"><span data-stu-id="73c73-102">DiscretePhaseEstimationIteration operation</span></span>

<span data-ttu-id="73c73-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="73c73-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="73c73-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73c73-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73c73-105">Bir Unitary Oracle 'ın tamsayı üslerini kullanarak yinelemeli (sınıflı kontrollü) bir aşama tahmin algoritmasının tek bir yinelemesini gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="73c73-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.</span></span>

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="73c73-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="73c73-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="73c73-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="73c73-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="73c73-108">$U ^ d $, bir tamsayı ve bir yazmaç üzerinde işlem gören, burada $U $, aşaması tahmin edilecek olan Unitary, ve $m $, Oracle 'a verilen tamsayı gücüne sahip olduğu bir kayıt.</span><span class="sxs-lookup"><span data-stu-id="73c73-108">Operation acting on an integer and a register, such that $U^m$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $m$ is the integer power given to the oracle</span></span>


### <a name="power--int"></a><span data-ttu-id="73c73-109">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="73c73-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="73c73-110">Verilen Unitary Oracle 'ın kaç kez uygulanacağını.</span><span class="sxs-lookup"><span data-stu-id="73c73-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="73c73-111">Teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="73c73-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="73c73-112">Hedef durum üzerinde işlem yapmadan önce denetim qubit üzerindeki aşamanın tersine çevirmek için kullanılacak açı.</span><span class="sxs-lookup"><span data-stu-id="73c73-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="73c73-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="73c73-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="73c73-114">Verilen Unitary Oracle tarafından üzerinde işlem yapılan durum kaydı.</span><span class="sxs-lookup"><span data-stu-id="73c73-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="73c73-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="73c73-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="73c73-116">Verilen Oracle 'ın uygulamasını denetlemek için kullanılan bir yardımcı qubit.</span><span class="sxs-lookup"><span data-stu-id="73c73-116">An auxiliary qubit used to control the application of the given oracle.</span></span>



## <a name="output--unit"></a><span data-ttu-id="73c73-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="73c73-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

