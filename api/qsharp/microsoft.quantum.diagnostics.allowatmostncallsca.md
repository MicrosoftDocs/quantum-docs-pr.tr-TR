---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853531"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="66e9d-102">AllowAtMostNCallsCA işlemi</span><span class="sxs-lookup"><span data-stu-id="66e9d-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="66e9d-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="66e9d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="66e9d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66e9d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66e9d-105">Bu işleme ve Adjoint çağrısı arasında, belirli bir işlemin en çok birkaç kez çağrıldığını onaylar.</span><span class="sxs-lookup"><span data-stu-id="66e9d-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="66e9d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="66e9d-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="66e9d-107">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="66e9d-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="66e9d-108">Çağrılabilen en fazla sayı `op` .</span><span class="sxs-lookup"><span data-stu-id="66e9d-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="66e9d-109">Op: ' TInput => ' TOutput, sıfatı + CTL</span><span class="sxs-lookup"><span data-stu-id="66e9d-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="66e9d-110">Çağrıları kısıtlanmış olan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="66e9d-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="66e9d-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="66e9d-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="66e9d-112">Hata durumunda görüntülenecek bir ileti.</span><span class="sxs-lookup"><span data-stu-id="66e9d-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="66e9d-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="66e9d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="66e9d-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="66e9d-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="66e9d-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="66e9d-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="66e9d-116">' TOutput</span><span class="sxs-lookup"><span data-stu-id="66e9d-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="66e9d-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="66e9d-117">Example</span></span>

<span data-ttu-id="66e9d-118">Aşağıdaki kod parçacığı, bu tanılamayı destekleyen makinelerde yürütüldüğünde başarısız olur:</span><span class="sxs-lookup"><span data-stu-id="66e9d-118">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="66e9d-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="66e9d-119">Remarks</span></span>

<span data-ttu-id="66e9d-120">Bu işlem, onu desteklemeyen hedefler üzerinde bir işleç ile değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="66e9d-120">This operation may be replaced by a no-op on targets which do not support it.</span></span>