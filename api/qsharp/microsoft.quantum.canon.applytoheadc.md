---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3a65ad52e0b2f8b3a921fc549c35311f24d0e189
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850622"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="73083-102">ApplyToHeadC işlemi</span><span class="sxs-lookup"><span data-stu-id="73083-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="73083-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="73083-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="73083-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73083-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73083-105">Bir işlemi bir dizinin ilk öğesine uygular.</span><span class="sxs-lookup"><span data-stu-id="73083-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="73083-106">Description</span><span class="sxs-lookup"><span data-stu-id="73083-106">Description</span></span>

<span data-ttu-id="73083-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="73083-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="73083-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="73083-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="73083-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="73083-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="73083-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="73083-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="73083-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="73083-111">targets : 'T[]</span></span>

<span data-ttu-id="73083-112">İlki uygulanacak bir dizi hedef `op` .</span><span class="sxs-lookup"><span data-stu-id="73083-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="73083-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="73083-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="73083-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="73083-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="73083-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="73083-115">'T</span></span>

<span data-ttu-id="73083-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="73083-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="73083-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="73083-117">See Also</span></span>

- [<span data-ttu-id="73083-118">Microsoft. hisse. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="73083-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="73083-119">Microsoft. hisse. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="73083-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="73083-120">Microsoft. hisse. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="73083-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)