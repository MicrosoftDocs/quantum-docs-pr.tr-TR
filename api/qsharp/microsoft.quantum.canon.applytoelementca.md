---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 599a8afe1ab97b0ab0d6621cabd7707faaeddda3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729246"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="87c53-102">ApplyToElementCA işlemi</span><span class="sxs-lookup"><span data-stu-id="87c53-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="87c53-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="87c53-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="87c53-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87c53-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87c53-105">Bir dizinin belirli bir öğesine bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="87c53-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="87c53-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="87c53-106">Description</span></span>

<span data-ttu-id="87c53-107">Bir işlem `op` , dizin ve bir `index` hedef dizisi verildiğinde `targets` , geçerlidir `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="87c53-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="87c53-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="87c53-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="87c53-109">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="87c53-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="87c53-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="87c53-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="87c53-111">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87c53-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87c53-112">Hedef dizisine bir dizin.</span><span class="sxs-lookup"><span data-stu-id="87c53-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="87c53-113">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="87c53-113">targets : 'T[]</span></span>

<span data-ttu-id="87c53-114">İçin olası hedeflerin bir dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="87c53-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="87c53-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="87c53-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="87c53-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="87c53-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="87c53-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="87c53-117">'T</span></span>

<span data-ttu-id="87c53-118">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="87c53-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="87c53-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="87c53-119">See Also</span></span>

- [<span data-ttu-id="87c53-120">Microsoft. hisse. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="87c53-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="87c53-121">Microsoft. hisse. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="87c53-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="87c53-122">Microsoft. hisse. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="87c53-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)