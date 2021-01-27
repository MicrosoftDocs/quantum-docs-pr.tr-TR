---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Assertprobınt işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843398"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="88e57-102">Assertprobınt işlemi</span><span class="sxs-lookup"><span data-stu-id="88e57-102">AssertProbInt operation</span></span>

<span data-ttu-id="88e57-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="88e57-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="88e57-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88e57-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88e57-105">Bir hisse amacının belirli bir durumunun beklenen değere sahip olma olasılığını onaylar.</span><span class="sxs-lookup"><span data-stu-id="88e57-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="88e57-106">Description</span><span class="sxs-lookup"><span data-stu-id="88e57-106">Description</span></span>

<span data-ttu-id="88e57-107">Bir $n $-qubit hisse durumu $ \ket{\psı} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $ olarak verildiğinde, $j $ tarafından dizini oluşturulan $ \ket{j} $ durumunun $ | \ alpha_j | ^ 2 $ değerinin beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="88e57-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="88e57-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="88e57-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="88e57-109">Stateındex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="88e57-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="88e57-110">Bir yazmaç tarafından temsil edilen $ \ket{j} $ durumunun $j $ dizini `LittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="88e57-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="88e57-111">beklenen: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="88e57-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="88e57-112">$ | \ Alpha_j | ^ 2 $ değerinin beklenen değeri.</span><span class="sxs-lookup"><span data-stu-id="88e57-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="88e57-113">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="88e57-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="88e57-114">$ \Ket{\psı} $ ' i küçük endian biçiminde depolayan qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="88e57-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="88e57-115">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="88e57-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="88e57-116">Gerçek ve beklenen arasındaki fark için mutlak tolerans.</span><span class="sxs-lookup"><span data-stu-id="88e57-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="88e57-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="88e57-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="88e57-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="88e57-118">Example</span></span>

<span data-ttu-id="88e57-119">`qubits`Yazmacın bir 3-qubit hisse durumu $ \ket{\psı} = \ sqrt {1/8} \ {0} Tus+ \ sqrt {7/8} \ hayvan {6} $ ' i küçük endian biçiminde kodluyor olduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="88e57-119">Suppose that the `qubits` register encodes a 3-qubit quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{6}$ in little-endian format.</span></span>
<span data-ttu-id="88e57-120">Bu sayı, $ \ ayraç {0} \ equiv\ayraç \ ayraç {0} {0} \ {0} ve $ \ ayraç {6} \ equiv\ayraç {0} \ {1} {1} ayraç \</span><span class="sxs-lookup"><span data-stu-id="88e57-120">This means that the number states $\ket{0}\equiv\ket{0}\ket{0}\ket{0}$ and $\ket{6}\equiv\ket{0}\ket{1}\ket{1}$.</span></span> <span data-ttu-id="88e57-121">Ardından, aşağıdaki onaylar başarılı olur:</span><span class="sxs-lookup"><span data-stu-id="88e57-121">Then the following asserts succeed:</span></span>

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```