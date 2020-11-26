---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: ApplyIfOneC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 24a00d83c1bbe6b07adb27c58fc70bc76af0a910
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209434"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="990cd-102">ApplyIfOneC işlemi</span><span class="sxs-lookup"><span data-stu-id="990cd-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="990cd-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="990cd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="990cd-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="990cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="990cd-105">Klasik sonuç değeri bir olan denetlenebilir bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="990cd-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="990cd-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="990cd-106">Description</span></span>

<span data-ttu-id="990cd-107">Bir işlem `op` ve sonuç değeri verildiğinde, `result` if ise `op` için geçerlidir `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="990cd-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="990cd-108">Varsa, `Zero` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="990cd-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="990cd-109">Sonek, `C` uygulanacak işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="990cd-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="990cd-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="990cd-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="990cd-111">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="990cd-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="990cd-112">Op 'ın uygulanıp uygulanmadığını denetleyen ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="990cd-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="990cd-113">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="990cd-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="990cd-114">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="990cd-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="990cd-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="990cd-115">target : 'T</span></span>

<span data-ttu-id="990cd-116">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="990cd-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="990cd-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="990cd-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="990cd-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="990cd-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="990cd-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="990cd-119">'T</span></span>

<span data-ttu-id="990cd-120">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="990cd-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="990cd-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="990cd-121">See Also</span></span>

- [<span data-ttu-id="990cd-122">Microsoft. hisse. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="990cd-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="990cd-123">Microsoft. hisse. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="990cd-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="990cd-124">Microsoft. hisse. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="990cd-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)