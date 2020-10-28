---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727367"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="4a10b-102">AllowAtMostNQubits işlemi</span><span class="sxs-lookup"><span data-stu-id="4a10b-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="4a10b-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4a10b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4a10b-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4a10b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4a10b-105">Bu işleme ve adeklem çağrısı arasında, using deyimleri ile verilen sayıda ek qubit için en fazla bir kaç sayının ayrıldığını onaylar.</span><span class="sxs-lookup"><span data-stu-id="4a10b-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="4a10b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4a10b-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="4a10b-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4a10b-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4a10b-108">Ayrılabilen en fazla qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="4a10b-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="4a10b-109">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4a10b-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4a10b-110">Hata durumunda görüntülenecek bir ileti.</span><span class="sxs-lookup"><span data-stu-id="4a10b-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a10b-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a10b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4a10b-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4a10b-112">Remarks</span></span>

<span data-ttu-id="4a10b-113">Bu işlem, onu desteklemeyen hedefler üzerinde bir işleç ile değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="4a10b-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>