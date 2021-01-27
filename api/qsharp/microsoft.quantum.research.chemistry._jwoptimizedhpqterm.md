---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedHpqTerm
title: _JWOptimizedHpqTerm işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedHpqTerm
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: b008315ded7cabc085e6d5da8f646e92914bf743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854806"
---
# <a name="_jwoptimizedhpqterm-operation"></a><span data-ttu-id="25c90-102">_JWOptimizedHpqTerm işlemi</span><span class="sxs-lookup"><span data-stu-id="25c90-102">_JWOptimizedHpqTerm operation</span></span>

<span data-ttu-id="25c90-103">Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="25c90-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="25c90-104">Paket: [Microsoft. hisse. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="25c90-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="25c90-105">Tarafından tanımlanan bir PQ terimiyle saat evrimi uygular `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="25c90-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedHpqTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="25c90-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="25c90-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="25c90-107">terim: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="25c90-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="25c90-108">`GeneratorIndex` PQ terimini temsil eden.</span><span class="sxs-lookup"><span data-stu-id="25c90-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="25c90-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="25c90-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="25c90-110">Zaman evrimi süresi.</span><span class="sxs-lookup"><span data-stu-id="25c90-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="25c90-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="25c90-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="25c90-112">Zaman evrimi 'nin işaretini belirleyen qubit.</span><span class="sxs-lookup"><span data-stu-id="25c90-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="25c90-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="25c90-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="25c90-114">Hamiltonian, qubit.</span><span class="sxs-lookup"><span data-stu-id="25c90-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25c90-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25c90-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

