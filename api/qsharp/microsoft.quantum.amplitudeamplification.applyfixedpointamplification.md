---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Applyfixedpoinkurname işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: f506be7b2e3f65cf89694e30d79c04ec30d25035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732023"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="bbd97-102">Applyfixedpoinkurname işlemi</span><span class="sxs-lookup"><span data-stu-id="bbd97-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="bbd97-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="bbd97-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="bbd97-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bbd97-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bbd97-105">Fixed-Point genliği yükseltme algoritması</span><span class="sxs-lookup"><span data-stu-id="bbd97-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="bbd97-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="bbd97-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="bbd97-107">statePrepOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="bbd97-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="bbd97-108">Başlangıç durumunu hazırlayan, Unitary Oracle.</span><span class="sxs-lookup"><span data-stu-id="bbd97-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="bbd97-109">startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bbd97-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bbd97-110">Qubit kayıt</span><span class="sxs-lookup"><span data-stu-id="bbd97-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="bbd97-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bbd97-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bbd97-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bbd97-112">Remarks</span></span>

<span data-ttu-id="bbd97-113">StartQubits $ \ket{0 \cnoktalar 0} $ durumunda olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="bbd97-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="bbd97-114">Bu işlem, bir dizi sorguya ulaşılıncaya veya hedef durum bulunana kadar $2 $ üsleri üzerinde birkaç sorgu üzerinde yinelenir.</span><span class="sxs-lookup"><span data-stu-id="bbd97-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>