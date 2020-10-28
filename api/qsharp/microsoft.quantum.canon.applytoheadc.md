---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3ff6c25837f1219dd456bf1739a2953ff72e2df9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729162"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="463b1-102">ApplyToHeadC işlemi</span><span class="sxs-lookup"><span data-stu-id="463b1-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="463b1-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="463b1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="463b1-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="463b1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="463b1-105">Bir işlemi bir dizinin ilk öğesine uygular.</span><span class="sxs-lookup"><span data-stu-id="463b1-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="463b1-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="463b1-106">Description</span></span>

<span data-ttu-id="463b1-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="463b1-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="463b1-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="463b1-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="463b1-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="463b1-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="463b1-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="463b1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="463b1-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="463b1-111">targets : 'T[]</span></span>

<span data-ttu-id="463b1-112">İlki uygulanacak bir dizi hedef `op` .</span><span class="sxs-lookup"><span data-stu-id="463b1-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="463b1-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="463b1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="463b1-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="463b1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="463b1-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="463b1-115">'T</span></span>

<span data-ttu-id="463b1-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="463b1-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="463b1-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="463b1-117">See Also</span></span>

- [<span data-ttu-id="463b1-118">Microsoft. hisse. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="463b1-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="463b1-119">Microsoft. hisse. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="463b1-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="463b1-120">Microsoft. hisse. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="463b1-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)