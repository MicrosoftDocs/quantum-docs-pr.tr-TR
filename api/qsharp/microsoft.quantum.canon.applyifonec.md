---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: ApplyIfOneC işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: ebeec5b46567892ad30f194ababb42876ba08bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841748"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="eab46-102">ApplyIfOneC işlemi</span><span class="sxs-lookup"><span data-stu-id="eab46-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="eab46-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eab46-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eab46-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eab46-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eab46-105">Klasik sonuç değeri bir olan denetlenebilir bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="eab46-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="eab46-106">Description</span><span class="sxs-lookup"><span data-stu-id="eab46-106">Description</span></span>

<span data-ttu-id="eab46-107">Bir işlem `op` ve sonuç değeri verildiğinde, `result` if ise `op` için geçerlidir `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="eab46-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="eab46-108">Varsa, `Zero` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="eab46-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="eab46-109">Sonek, `C` uygulanacak işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="eab46-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="eab46-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="eab46-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="eab46-111">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="eab46-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="eab46-112">Op 'ın uygulanıp uygulanmadığını denetleyen ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="eab46-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="eab46-113">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="eab46-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="eab46-114">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="eab46-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="eab46-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="eab46-115">target : 'T</span></span>

<span data-ttu-id="eab46-116">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="eab46-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eab46-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eab46-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eab46-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="eab46-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eab46-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="eab46-119">'T</span></span>

<span data-ttu-id="eab46-120">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="eab46-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="eab46-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="eab46-121">See Also</span></span>

- [<span data-ttu-id="eab46-122">Microsoft. hisse. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="eab46-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="eab46-123">Microsoft. hisse. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="eab46-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="eab46-124">Microsoft. hisse. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="eab46-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)