---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: ApplyIfOneCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 973dd3c5f9f3e9ad03c0626a38779f499b7ce657
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729515"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="72edb-102">ApplyIfOneCA işlemi</span><span class="sxs-lookup"><span data-stu-id="72edb-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="72edb-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="72edb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="72edb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72edb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72edb-105">Klasik sonuç değeri bir olan bir Unitary işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="72edb-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="72edb-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="72edb-106">Description</span></span>

<span data-ttu-id="72edb-107">Bir işlem `op` ve sonuç değeri verildiğinde, `result` if ise `op` için geçerlidir `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="72edb-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="72edb-108">Varsa, `Zero` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="72edb-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="72edb-109">Sonek, `CA` uygulanacak işlemin Unitary (denetlenebilir ve adjointable) olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="72edb-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="72edb-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="72edb-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="72edb-111">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="72edb-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="72edb-112">Op 'ın uygulanıp uygulanmadığını denetleyen ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="72edb-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="72edb-113">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="72edb-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="72edb-114">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="72edb-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="72edb-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="72edb-115">target : 'T</span></span>

<span data-ttu-id="72edb-116">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="72edb-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72edb-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72edb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="72edb-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="72edb-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="72edb-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="72edb-119">'T</span></span>

<span data-ttu-id="72edb-120">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="72edb-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="72edb-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="72edb-121">See Also</span></span>

- [<span data-ttu-id="72edb-122">Microsoft. hisse. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="72edb-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="72edb-123">Microsoft. hisse. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="72edb-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="72edb-124">Microsoft. hisse. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="72edb-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)