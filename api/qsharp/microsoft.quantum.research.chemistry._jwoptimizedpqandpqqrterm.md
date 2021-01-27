---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedPQandPQQRTerm
title: _JWOptimizedPQandPQQRTerm işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedPQandPQQRTerm
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: 97ae285ede38883f058b3e7609f9a26fb9e4340a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854768"
---
# <a name="_jwoptimizedpqandpqqrterm-operation"></a><span data-ttu-id="773d1-102">_JWOptimizedPQandPQQRTerm işlemi</span><span class="sxs-lookup"><span data-stu-id="773d1-102">_JWOptimizedPQandPQQRTerm operation</span></span>

<span data-ttu-id="773d1-103">Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="773d1-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="773d1-104">Paket: [Microsoft. hisse. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="773d1-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="773d1-105">Bir PQ veya PQQR teriminin bir tarafından tanımlanan zaman gelişimini uygular `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="773d1-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedPQandPQQRTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="773d1-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="773d1-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="773d1-107">terim: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="773d1-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="773d1-108">`GeneratorIndex` PQ veya PQQr terimini temsil etme.</span><span class="sxs-lookup"><span data-stu-id="773d1-108">`GeneratorIndex` representing a PQ or PQQr term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="773d1-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="773d1-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="773d1-110">Zaman evrimi süresi.</span><span class="sxs-lookup"><span data-stu-id="773d1-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="773d1-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="773d1-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="773d1-112">Zaman evrimi 'nin işaretini belirleyen qubit.</span><span class="sxs-lookup"><span data-stu-id="773d1-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="773d1-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="773d1-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="773d1-114">Hamiltonian, qubit.</span><span class="sxs-lookup"><span data-stu-id="773d1-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="773d1-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="773d1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

