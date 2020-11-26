---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Applyfixedpoinkurname işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: 13e70b1ebd5e3bf0996e6a76f4bffe57ca2d2250
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191542"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="a457e-102">Applyfixedpoinkurname işlemi</span><span class="sxs-lookup"><span data-stu-id="a457e-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="a457e-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="a457e-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="a457e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a457e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a457e-105">Fixed-Point genliği yükseltme algoritması</span><span class="sxs-lookup"><span data-stu-id="a457e-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a457e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a457e-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="a457e-107">statePrepOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="a457e-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="a457e-108">Başlangıç durumunu hazırlayan, Unitary Oracle.</span><span class="sxs-lookup"><span data-stu-id="a457e-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="a457e-109">startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a457e-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a457e-110">Qubit kayıt</span><span class="sxs-lookup"><span data-stu-id="a457e-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="a457e-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a457e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a457e-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a457e-112">Remarks</span></span>

<span data-ttu-id="a457e-113">StartQubits $ \ket{0 \cnoktalar 0} $ durumunda olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a457e-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="a457e-114">Bu işlem, bir dizi sorguya ulaşılıncaya veya hedef durum bulunana kadar $2 $ üsleri üzerinde birkaç sorgu üzerinde yinelenir.</span><span class="sxs-lookup"><span data-stu-id="a457e-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>