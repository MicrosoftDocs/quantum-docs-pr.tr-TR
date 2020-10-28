---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: ApplyIfZero işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 7435150937143a8d1a67afe334b683932a9655de
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729510"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="4e542-102">ApplyIfZero işlemi</span><span class="sxs-lookup"><span data-stu-id="4e542-102">ApplyIfZero operation</span></span>

<span data-ttu-id="4e542-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4e542-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4e542-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e542-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e542-105">Klasik sonuç değeri sıfır olan bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="4e542-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="4e542-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4e542-106">Description</span></span>

<span data-ttu-id="4e542-107">Bir işlem `op` ve sonuç değeri verildiğinde, `result` if ise `op` için geçerlidir `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="4e542-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="4e542-108">Varsa, `One` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="4e542-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="4e542-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="4e542-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="4e542-110">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="4e542-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="4e542-111">Op 'ın uygulanıp uygulanmadığını denetleyen ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="4e542-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="4e542-112">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e542-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4e542-113">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="4e542-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="4e542-114">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="4e542-114">target : 'T</span></span>

<span data-ttu-id="4e542-115">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="4e542-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4e542-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e542-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4e542-117">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="4e542-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4e542-118">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="4e542-118">'T</span></span>

<span data-ttu-id="4e542-119">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="4e542-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e542-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4e542-120">See Also</span></span>

- [<span data-ttu-id="4e542-121">Microsoft. hisse. Canon. Applyifsıfırlaması c</span><span class="sxs-lookup"><span data-stu-id="4e542-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="4e542-122">Microsoft. hisse. Canon. Applyifsıfırlaması a</span><span class="sxs-lookup"><span data-stu-id="4e542-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="4e542-123">Microsoft. hisse. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="4e542-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)