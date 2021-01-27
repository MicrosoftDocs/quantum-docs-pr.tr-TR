---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 1bb24006a2d52167dfc7a7871cfbf5a4378d1cb7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850609"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="d3dd6-102">ApplyToHeadCA işlemi</span><span class="sxs-lookup"><span data-stu-id="d3dd6-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="d3dd6-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d3dd6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d3dd6-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3dd6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3dd6-105">Bir işlemi bir dizinin ilk öğesine uygular.</span><span class="sxs-lookup"><span data-stu-id="d3dd6-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d3dd6-106">Description</span><span class="sxs-lookup"><span data-stu-id="d3dd6-106">Description</span></span>

<span data-ttu-id="d3dd6-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="d3dd6-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d3dd6-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="d3dd6-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="d3dd6-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="d3dd6-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d3dd6-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="d3dd6-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d3dd6-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="d3dd6-111">targets : 'T[]</span></span>

<span data-ttu-id="d3dd6-112">İlki uygulanacak bir dizi hedef `op` .</span><span class="sxs-lookup"><span data-stu-id="d3dd6-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3dd6-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3dd6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d3dd6-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="d3dd6-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d3dd6-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="d3dd6-115">'T</span></span>

<span data-ttu-id="d3dd6-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="d3dd6-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3dd6-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d3dd6-117">See Also</span></span>

- [<span data-ttu-id="d3dd6-118">Microsoft. hisse. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="d3dd6-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="d3dd6-119">Microsoft. hisse. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="d3dd6-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="d3dd6-120">Microsoft. hisse. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="d3dd6-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)