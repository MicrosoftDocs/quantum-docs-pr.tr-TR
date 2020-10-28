---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Assertprobınt işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731679"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="fc501-102">Assertprobınt işlemi</span><span class="sxs-lookup"><span data-stu-id="fc501-102">AssertProbInt operation</span></span>

<span data-ttu-id="fc501-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fc501-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fc501-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fc501-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fc501-105">Bir hisse amacının belirli bir durumunun beklenen değere sahip olma olasılığını onaylar.</span><span class="sxs-lookup"><span data-stu-id="fc501-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="fc501-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="fc501-106">Description</span></span>

<span data-ttu-id="fc501-107">Bir $n $-qubit hisse durumu $ \ket{\psı} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $ olarak verildiğinde, $j $ tarafından dizini oluşturulan $ \ket{j} $ durumunun $ | \ alpha_j | ^ 2 $ değerinin beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="fc501-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="fc501-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="fc501-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="fc501-109">Stateındex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc501-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fc501-110">Bir yazmaç tarafından temsil edilen $ \ket{j} $ durumunun $j $ dizini `LittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="fc501-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="fc501-111">beklenen: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fc501-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fc501-112">$ | \ Alpha_j | ^ 2 $ değerinin beklenen değeri.</span><span class="sxs-lookup"><span data-stu-id="fc501-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="fc501-113">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fc501-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fc501-114">$ \Ket{\psı} $ ' i küçük endian biçiminde depolayan qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="fc501-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="fc501-115">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fc501-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fc501-116">Gerçek ve beklenen arasındaki fark için mutlak tolerans.</span><span class="sxs-lookup"><span data-stu-id="fc501-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fc501-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc501-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

