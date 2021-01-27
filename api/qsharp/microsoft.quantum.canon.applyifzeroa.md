---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: Applyifsıfırlama bir işlem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: 23c494d144ef61d40c3ca7a5de452472ffa70335
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844900"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="3e5e9-102">Applyifsıfırlama bir işlem</span><span class="sxs-lookup"><span data-stu-id="3e5e9-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="3e5e9-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3e5e9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3e5e9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e5e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e5e9-105">Klasik sonuç değeri sıfır olan bir adjointable işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="3e5e9-105">Applies an adjointable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="3e5e9-106">Description</span><span class="sxs-lookup"><span data-stu-id="3e5e9-106">Description</span></span>

<span data-ttu-id="3e5e9-107">Bir işlem `op` ve sonuç değeri verildiğinde, `result` if ise `op` için geçerlidir `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="3e5e9-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="3e5e9-108">Varsa, `One` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="3e5e9-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="3e5e9-109">Sonek, `A` uygulanacak işlemin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="3e5e9-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="3e5e9-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="3e5e9-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="3e5e9-111">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="3e5e9-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="3e5e9-112">Op 'ın uygulanıp uygulanmadığını denetleyen ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="3e5e9-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="3e5e9-113">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="3e5e9-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3e5e9-114">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="3e5e9-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="3e5e9-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="3e5e9-115">target : 'T</span></span>

<span data-ttu-id="3e5e9-116">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="3e5e9-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e5e9-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e5e9-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3e5e9-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="3e5e9-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3e5e9-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="3e5e9-119">'T</span></span>

<span data-ttu-id="3e5e9-120">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="3e5e9-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e5e9-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3e5e9-121">See Also</span></span>

- [<span data-ttu-id="3e5e9-122">Microsoft. hisse. Canon. Applyifsıfırlaması c</span><span class="sxs-lookup"><span data-stu-id="3e5e9-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="3e5e9-123">Microsoft. hisse. Canon. Applyifsıfırlaması a</span><span class="sxs-lookup"><span data-stu-id="3e5e9-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="3e5e9-124">Microsoft. hisse. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="3e5e9-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)