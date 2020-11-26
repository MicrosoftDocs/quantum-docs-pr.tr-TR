---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 7caf33e33318bb74cb160436940eff9f0f2782cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202575"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="40783-102">AllowAtMostNCallsCA işlemi</span><span class="sxs-lookup"><span data-stu-id="40783-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="40783-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="40783-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="40783-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="40783-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="40783-105">Bu işleme ve Adjoint çağrısı arasında, belirli bir işlemin en çok birkaç kez çağrıldığını onaylar.</span><span class="sxs-lookup"><span data-stu-id="40783-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="40783-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="40783-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="40783-107">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="40783-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="40783-108">Çağrılabilen en fazla sayı `op` .</span><span class="sxs-lookup"><span data-stu-id="40783-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="40783-109">Op: ' TInput => ' TOutput, sıfatı + CTL</span><span class="sxs-lookup"><span data-stu-id="40783-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="40783-110">Çağrıları kısıtlanmış olan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="40783-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="40783-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="40783-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="40783-112">Hata durumunda görüntülenecek bir ileti.</span><span class="sxs-lookup"><span data-stu-id="40783-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="40783-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40783-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="40783-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="40783-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="40783-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="40783-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="40783-116">' TOutput</span><span class="sxs-lookup"><span data-stu-id="40783-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="40783-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="40783-117">Remarks</span></span>

<span data-ttu-id="40783-118">Bu işlem, onu desteklemeyen hedefler üzerinde bir işleç ile değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="40783-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>