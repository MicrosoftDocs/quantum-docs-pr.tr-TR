---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727368"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="3ce5c-102">AllowAtMostNCallsCA işlemi</span><span class="sxs-lookup"><span data-stu-id="3ce5c-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="3ce5c-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="3ce5c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="3ce5c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ce5c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3ce5c-105">Bu işleme ve Adjoint çağrısı arasında, belirli bir işlemin en çok birkaç kez çağrıldığını onaylar.</span><span class="sxs-lookup"><span data-stu-id="3ce5c-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="3ce5c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3ce5c-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="3ce5c-107">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ce5c-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ce5c-108">Çağrılabilen en fazla sayı `op` .</span><span class="sxs-lookup"><span data-stu-id="3ce5c-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput-adj--ctl"></a><span data-ttu-id="3ce5c-109">Op: ' TInput => ' TOutput ayarlama + CTL</span><span class="sxs-lookup"><span data-stu-id="3ce5c-109">op : 'TInput => 'TOutput Adj + Ctl</span></span>

<span data-ttu-id="3ce5c-110">Çağrıları kısıtlanmış olan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="3ce5c-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="3ce5c-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="3ce5c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="3ce5c-112">Hata durumunda görüntülenecek bir ileti.</span><span class="sxs-lookup"><span data-stu-id="3ce5c-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ce5c-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ce5c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3ce5c-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="3ce5c-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="3ce5c-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="3ce5c-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="3ce5c-116">' TOutput</span><span class="sxs-lookup"><span data-stu-id="3ce5c-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="3ce5c-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3ce5c-117">Remarks</span></span>

<span data-ttu-id="3ce5c-118">Bu işlem, onu desteklemeyen hedefler üzerinde bir işleç ile değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="3ce5c-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>