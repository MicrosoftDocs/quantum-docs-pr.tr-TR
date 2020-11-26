---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 5376b6f39d12d664342fbf71e67442c6ef8a0827
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202558"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="22f40-102">AllowAtMostNQubits işlemi</span><span class="sxs-lookup"><span data-stu-id="22f40-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="22f40-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="22f40-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="22f40-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22f40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22f40-105">Bu işleme ve adeklem çağrısı arasında, using deyimleri ile verilen sayıda ek qubit için en fazla bir kaç sayının ayrıldığını onaylar.</span><span class="sxs-lookup"><span data-stu-id="22f40-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="22f40-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="22f40-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="22f40-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="22f40-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="22f40-108">Ayrılabilen en fazla qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="22f40-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="22f40-109">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="22f40-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="22f40-110">Hata durumunda görüntülenecek bir ileti.</span><span class="sxs-lookup"><span data-stu-id="22f40-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="22f40-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="22f40-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="22f40-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="22f40-112">Remarks</span></span>

<span data-ttu-id="22f40-113">Bu işlem, onu desteklemeyen hedefler üzerinde bir işleç ile değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="22f40-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>