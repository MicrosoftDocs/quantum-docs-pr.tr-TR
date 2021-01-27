---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Estimatetermexeditation işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835665"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="e3eaa-102">Estimatetermexeditation işlemi</span><span class="sxs-lookup"><span data-stu-id="e3eaa-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="e3eaa-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="e3eaa-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="e3eaa-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e3eaa-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="e3eaa-105">Belirli bir Jordan-Wigner Hamiltonian terimiyle ilişkili enerjiyi hesaplar</span><span class="sxs-lookup"><span data-stu-id="e3eaa-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="e3eaa-106">Description</span><span class="sxs-lookup"><span data-stu-id="e3eaa-106">Description</span></span>

<span data-ttu-id="e3eaa-107">Bu işlem, her ölçüm işleciyle ilişkili beklenerek değeri tahmin eder ve örnekleme kullanarak karşılık gelen katsayısı ile çarpar.</span><span class="sxs-lookup"><span data-stu-id="e3eaa-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="e3eaa-108">Sonuçlar, Jordan-Wigner teriminin enerji düzeyini içeren bir değişkende toplanır.</span><span class="sxs-lookup"><span data-stu-id="e3eaa-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="e3eaa-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="e3eaa-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit--is-adj"></a><span data-ttu-id="e3eaa-110">ınputstateunitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="e3eaa-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e3eaa-111">Durum hazırlığı için kullanılan Unitary.</span><span class="sxs-lookup"><span data-stu-id="e3eaa-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="e3eaa-112">Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="e3eaa-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="e3eaa-113">Jordan-Wigner teriminin ölçüm işleçleri.</span><span class="sxs-lookup"><span data-stu-id="e3eaa-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="e3eaa-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e3eaa-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e3eaa-115">Jordan-Wigner teriminin katsayısıdır.</span><span class="sxs-lookup"><span data-stu-id="e3eaa-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="e3eaa-116">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e3eaa-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e3eaa-117">Molesel sistemin benzetimini yapmak için gereken qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="e3eaa-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="e3eaa-118">nSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e3eaa-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e3eaa-119">Beklenme teriminin tahmini için kullanılacak örneklerin sayısı.</span><span class="sxs-lookup"><span data-stu-id="e3eaa-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="e3eaa-120">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e3eaa-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e3eaa-121">Jordan-Wigner terimiyle ilişkilendirilen enerji.</span><span class="sxs-lookup"><span data-stu-id="e3eaa-121">The energy associated to the Jordan-Wigner term.</span></span>