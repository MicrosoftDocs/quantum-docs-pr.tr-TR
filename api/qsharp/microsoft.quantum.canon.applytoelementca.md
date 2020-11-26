---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8ae4ece0d3d56ea2be1ce494ab0c5ee7caacbbf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208865"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="232b0-102">ApplyToElementCA işlemi</span><span class="sxs-lookup"><span data-stu-id="232b0-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="232b0-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="232b0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="232b0-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="232b0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="232b0-105">Bir dizinin belirli bir öğesine bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="232b0-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="232b0-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="232b0-106">Description</span></span>

<span data-ttu-id="232b0-107">Bir işlem `op` , dizin ve bir `index` hedef dizisi verildiğinde `targets` , geçerlidir `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="232b0-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="232b0-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="232b0-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="232b0-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="232b0-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="232b0-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="232b0-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="232b0-111">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="232b0-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="232b0-112">Hedef dizisine bir dizin.</span><span class="sxs-lookup"><span data-stu-id="232b0-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="232b0-113">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="232b0-113">targets : 'T[]</span></span>

<span data-ttu-id="232b0-114">İçin olası hedeflerin bir dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="232b0-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="232b0-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="232b0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="232b0-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="232b0-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="232b0-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="232b0-117">'T</span></span>

<span data-ttu-id="232b0-118">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="232b0-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="232b0-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="232b0-119">See Also</span></span>

- [<span data-ttu-id="232b0-120">Microsoft. hisse. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="232b0-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="232b0-121">Microsoft. hisse. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="232b0-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="232b0-122">Microsoft. hisse. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="232b0-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)