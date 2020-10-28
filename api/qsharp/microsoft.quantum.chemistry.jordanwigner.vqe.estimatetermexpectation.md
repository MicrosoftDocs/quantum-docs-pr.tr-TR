---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Estimatetermexeditation işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727655"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="62025-102">Estimatetermexeditation işlemi</span><span class="sxs-lookup"><span data-stu-id="62025-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="62025-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="62025-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="62025-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62025-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="62025-105">Belirli bir Jordan-Wigner Hamiltonian terimiyle ilişkili enerjiyi hesaplar</span><span class="sxs-lookup"><span data-stu-id="62025-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="62025-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="62025-106">Description</span></span>

<span data-ttu-id="62025-107">Bu işlem, her ölçüm işleciyle ilişkili beklenerek değeri tahmin eder ve örnekleme kullanarak karşılık gelen katsayısı ile çarpar.</span><span class="sxs-lookup"><span data-stu-id="62025-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="62025-108">Sonuçlar, Jordan-Wigner teriminin enerji düzeyini içeren bir değişkende toplanır.</span><span class="sxs-lookup"><span data-stu-id="62025-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="62025-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="62025-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit-adj"></a><span data-ttu-id="62025-110">ınputstateunitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama</span><span class="sxs-lookup"><span data-stu-id="62025-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="62025-111">Durum hazırlığı için kullanılan Unitary.</span><span class="sxs-lookup"><span data-stu-id="62025-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="62025-112">Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="62025-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="62025-113">Jordan-Wigner teriminin ölçüm işleçleri.</span><span class="sxs-lookup"><span data-stu-id="62025-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="62025-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="62025-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="62025-115">Jordan-Wigner teriminin katsayısıdır.</span><span class="sxs-lookup"><span data-stu-id="62025-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="62025-116">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="62025-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="62025-117">Molesel sistemin benzetimini yapmak için gereken qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="62025-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="62025-118">nSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="62025-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="62025-119">Beklenme teriminin tahmini için kullanılacak örneklerin sayısı.</span><span class="sxs-lookup"><span data-stu-id="62025-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="62025-120">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="62025-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="62025-121">Jordan-Wigner terimiyle ilişkilendirilen enerji.</span><span class="sxs-lookup"><span data-stu-id="62025-121">The energy associated to the Jordan-Wigner term.</span></span>