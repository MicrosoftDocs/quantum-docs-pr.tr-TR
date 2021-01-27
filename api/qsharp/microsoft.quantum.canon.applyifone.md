---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: ApplyIfOne işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: b86aecf3dc3d02d1a6bf0c112bdc45a55a2cf087
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841775"
---
# <a name="applyifone-operation"></a><span data-ttu-id="b2e09-102">ApplyIfOne işlemi</span><span class="sxs-lookup"><span data-stu-id="b2e09-102">ApplyIfOne operation</span></span>

<span data-ttu-id="b2e09-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b2e09-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b2e09-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2e09-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2e09-105">Klasik sonuç değeri bir olan bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="b2e09-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="b2e09-106">Description</span><span class="sxs-lookup"><span data-stu-id="b2e09-106">Description</span></span>

<span data-ttu-id="b2e09-107">Bir işlem `op` ve sonuç değeri verildiğinde, `result` if ise `op` için geçerlidir `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="b2e09-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="b2e09-108">Varsa, `Zero` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="b2e09-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="b2e09-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="b2e09-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="b2e09-110">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="b2e09-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="b2e09-111">Op 'ın uygulanıp uygulanmadığını denetleyen ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="b2e09-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="b2e09-112">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2e09-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b2e09-113">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="b2e09-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="b2e09-114">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="b2e09-114">target : 'T</span></span>

<span data-ttu-id="b2e09-115">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="b2e09-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2e09-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2e09-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b2e09-117">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="b2e09-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b2e09-118">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="b2e09-118">'T</span></span>

<span data-ttu-id="b2e09-119">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="b2e09-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2e09-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b2e09-120">See Also</span></span>

- [<span data-ttu-id="b2e09-121">Microsoft. hisse. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="b2e09-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="b2e09-122">Microsoft. hisse. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="b2e09-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="b2e09-123">Microsoft. hisse. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="b2e09-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)