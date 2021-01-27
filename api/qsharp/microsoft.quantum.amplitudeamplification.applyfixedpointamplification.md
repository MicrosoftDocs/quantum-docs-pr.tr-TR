---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Applyfixedpoinkurname işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: fa19c3bb06ae91a2fa18acb6f853020830e749f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847227"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="73170-102">Applyfixedpoinkurname işlemi</span><span class="sxs-lookup"><span data-stu-id="73170-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="73170-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="73170-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="73170-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73170-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73170-105">Fixed-Point genliği yükseltme algoritması</span><span class="sxs-lookup"><span data-stu-id="73170-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="73170-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="73170-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="73170-107">statePrepOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="73170-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="73170-108">Başlangıç durumunu hazırlayan, Unitary Oracle.</span><span class="sxs-lookup"><span data-stu-id="73170-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="73170-109">startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="73170-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="73170-110">Qubit kayıt</span><span class="sxs-lookup"><span data-stu-id="73170-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="73170-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="73170-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="73170-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="73170-112">Remarks</span></span>

<span data-ttu-id="73170-113">StartQubits $ \ket{0 \cnoktalar 0} $ durumunda olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="73170-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="73170-114">Bu işlem, bir dizi sorguya ulaşılıncaya veya hedef durum bulunana kadar $2 $ üsleri üzerinde birkaç sorgu üzerinde yinelenir.</span><span class="sxs-lookup"><span data-stu-id="73170-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>