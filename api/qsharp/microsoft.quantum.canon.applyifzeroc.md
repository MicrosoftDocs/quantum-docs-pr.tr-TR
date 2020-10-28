---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: Applyifsıfırlaması c işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: cfc2a659f4da011baadff1a0d6a20a2a36d0a285
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729491"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="8454e-102">Applyifsıfırlaması c işlemi</span><span class="sxs-lookup"><span data-stu-id="8454e-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="8454e-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8454e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8454e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8454e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8454e-105">Klasik sonuç değeri sıfır olan denetlenebilir bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="8454e-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="8454e-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="8454e-106">Description</span></span>

<span data-ttu-id="8454e-107">Bir işlem `op` ve sonuç değeri verildiğinde, `result` if ise `op` için geçerlidir `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="8454e-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="8454e-108">Varsa, `One` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="8454e-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="8454e-109">Sonek, `C` uygulanacak işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="8454e-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="8454e-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="8454e-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="8454e-111">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="8454e-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="8454e-112">Op 'ın uygulanıp uygulanmadığını denetleyen ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="8454e-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="8454e-113">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="8454e-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="8454e-114">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="8454e-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="8454e-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="8454e-115">target : 'T</span></span>

<span data-ttu-id="8454e-116">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="8454e-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8454e-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8454e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8454e-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="8454e-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8454e-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="8454e-119">'T</span></span>

<span data-ttu-id="8454e-120">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="8454e-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8454e-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8454e-121">See Also</span></span>

- [<span data-ttu-id="8454e-122">Microsoft. hisse. Canon. Applyifsıfırlaması c</span><span class="sxs-lookup"><span data-stu-id="8454e-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="8454e-123">Microsoft. hisse. Canon. Applyifsıfırlaması a</span><span class="sxs-lookup"><span data-stu-id="8454e-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="8454e-124">Microsoft. hisse. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="8454e-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)