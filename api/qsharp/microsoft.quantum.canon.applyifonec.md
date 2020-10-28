---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: ApplyIfOneC işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 9a2e020c596b02d9cb38309d02ca02056c1dec75
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729522"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="e2068-102">ApplyIfOneC işlemi</span><span class="sxs-lookup"><span data-stu-id="e2068-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="e2068-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e2068-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e2068-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e2068-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e2068-105">Klasik sonuç değeri bir olan denetlenebilir bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="e2068-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="e2068-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e2068-106">Description</span></span>

<span data-ttu-id="e2068-107">Bir işlem `op` ve sonuç değeri verildiğinde, `result` if ise `op` için geçerlidir `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="e2068-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="e2068-108">Varsa, `Zero` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="e2068-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="e2068-109">Sonek, `C` uygulanacak işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="e2068-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="e2068-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="e2068-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="e2068-111">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="e2068-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="e2068-112">Op 'ın uygulanıp uygulanmadığını denetleyen ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="e2068-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="e2068-113">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="e2068-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="e2068-114">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="e2068-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="e2068-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="e2068-115">target : 'T</span></span>

<span data-ttu-id="e2068-116">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="e2068-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e2068-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e2068-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e2068-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e2068-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e2068-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e2068-119">'T</span></span>

<span data-ttu-id="e2068-120">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="e2068-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2068-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e2068-121">See Also</span></span>

- [<span data-ttu-id="e2068-122">Microsoft. hisse. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="e2068-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="e2068-123">Microsoft. hisse. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="e2068-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="e2068-124">Microsoft. hisse. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="e2068-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)