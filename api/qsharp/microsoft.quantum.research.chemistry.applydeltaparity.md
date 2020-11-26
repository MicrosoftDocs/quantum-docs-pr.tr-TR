---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Applydeltaeşliği işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: 40157b6a166b09c6fee63d86e203f92069d008f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225763"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="f7c7d-102">Applydeltaeşliği işlemi</span><span class="sxs-lookup"><span data-stu-id="f7c7d-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="f7c7d-103">Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f7c7d-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="f7c7d-104">Paket: [Microsoft. hisse. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f7c7d-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="f7c7d-105">Önceki bir PQRS arasındaki eşlik farkını hesaplar... hüküm ve sonraki PQRS... terimli.</span><span class="sxs-lookup"><span data-stu-id="f7c7d-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="f7c7d-106">Bu fark, bir yardımcı qubit üzerinde hesaplanır.</span><span class="sxs-lookup"><span data-stu-id="f7c7d-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f7c7d-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="f7c7d-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="f7c7d-108">Prevfermıonicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f7c7d-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f7c7d-109">Önceki PQRS için dizinlerin listesi... larındaki.</span><span class="sxs-lookup"><span data-stu-id="f7c7d-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="f7c7d-110">Nextfermıonicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f7c7d-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f7c7d-111">Sonraki PQRS için dizinlerin listesi... larındaki.</span><span class="sxs-lookup"><span data-stu-id="f7c7d-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="f7c7d-112">Aux: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f7c7d-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f7c7d-113">Eşlik hesaplama sonuçlarının depolandığı yardımcı qubit.</span><span class="sxs-lookup"><span data-stu-id="f7c7d-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f7c7d-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f7c7d-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f7c7d-115">Qubit, tüm PQRS tarafından üzerinde işlem yaptığı... larındaki.</span><span class="sxs-lookup"><span data-stu-id="f7c7d-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7c7d-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7c7d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f7c7d-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f7c7d-117">Remarks</span></span>

<span data-ttu-id="f7c7d-118">Bu, P < Q < R < S 'nin dizinlerinin < olduğunu varsayar... hem prevPQ hem de nextPQ için.</span><span class="sxs-lookup"><span data-stu-id="f7c7d-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>