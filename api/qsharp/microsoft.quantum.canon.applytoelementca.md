---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 420a92ae10d2fc260024968b1846e669c4b62d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841463"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="4858f-102">ApplyToElementCA işlemi</span><span class="sxs-lookup"><span data-stu-id="4858f-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="4858f-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4858f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4858f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4858f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4858f-105">Bir dizinin belirli bir öğesine bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="4858f-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4858f-106">Description</span><span class="sxs-lookup"><span data-stu-id="4858f-106">Description</span></span>

<span data-ttu-id="4858f-107">Bir işlem `op` , dizin ve bir `index` hedef dizisi verildiğinde `targets` , geçerlidir `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="4858f-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="4858f-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="4858f-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="4858f-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="4858f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4858f-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="4858f-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="4858f-111">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4858f-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4858f-112">Hedef dizisine bir dizin.</span><span class="sxs-lookup"><span data-stu-id="4858f-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4858f-113">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="4858f-113">targets : 'T[]</span></span>

<span data-ttu-id="4858f-114">İçin olası hedeflerin bir dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="4858f-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4858f-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4858f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4858f-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="4858f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4858f-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="4858f-117">'T</span></span>

<span data-ttu-id="4858f-118">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="4858f-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4858f-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4858f-119">See Also</span></span>

- [<span data-ttu-id="4858f-120">Microsoft. hisse. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="4858f-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="4858f-121">Microsoft. hisse. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="4858f-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="4858f-122">Microsoft. hisse. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="4858f-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)