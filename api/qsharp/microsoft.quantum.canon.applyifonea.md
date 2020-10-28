---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: ApplyIfOneA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 76c15aba6042c2801ecfe8470e82099c54ba3846
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729527"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="83472-102">ApplyIfOneA işlemi</span><span class="sxs-lookup"><span data-stu-id="83472-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="83472-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="83472-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="83472-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="83472-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="83472-105">Bir klasik sonuç değeri olan bir adjointable işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="83472-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="83472-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="83472-106">Description</span></span>

<span data-ttu-id="83472-107">Bir işlem `op` ve sonuç değeri verildiğinde, `result` if ise `op` için geçerlidir `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="83472-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="83472-108">Varsa, `Zero` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="83472-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="83472-109">Sonek, `A` uygulanacak işlemin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="83472-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="83472-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="83472-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="83472-111">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="83472-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="83472-112">Op 'ın uygulanıp uygulanmadığını denetleyen ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="83472-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="83472-113">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="83472-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="83472-114">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="83472-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="83472-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="83472-115">target : 'T</span></span>

<span data-ttu-id="83472-116">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="83472-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="83472-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="83472-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="83472-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="83472-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="83472-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="83472-119">'T</span></span>

<span data-ttu-id="83472-120">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="83472-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="83472-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="83472-121">See Also</span></span>

- [<span data-ttu-id="83472-122">Microsoft. hisse. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="83472-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="83472-123">Microsoft. hisse. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="83472-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="83472-124">Microsoft. hisse. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="83472-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)