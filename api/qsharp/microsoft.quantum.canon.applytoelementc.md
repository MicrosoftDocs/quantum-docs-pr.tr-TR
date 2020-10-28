---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bd466ff59e6e962be9a7e58b6d298c60b0d1d90d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729251"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="ec10a-102">ApplyToElementC işlemi</span><span class="sxs-lookup"><span data-stu-id="ec10a-102">ApplyToElementC operation</span></span>

<span data-ttu-id="ec10a-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ec10a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ec10a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ec10a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ec10a-105">Bir dizinin belirli bir öğesine bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="ec10a-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ec10a-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ec10a-106">Description</span></span>

<span data-ttu-id="ec10a-107">Bir işlem `op` , dizin ve bir `index` hedef dizisi verildiğinde `targets` , geçerlidir `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="ec10a-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="ec10a-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="ec10a-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="ec10a-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="ec10a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="ec10a-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="ec10a-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="ec10a-111">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ec10a-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ec10a-112">Hedef dizisine bir dizin.</span><span class="sxs-lookup"><span data-stu-id="ec10a-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ec10a-113">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="ec10a-113">targets : 'T[]</span></span>

<span data-ttu-id="ec10a-114">İçin olası hedeflerin bir dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="ec10a-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ec10a-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec10a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ec10a-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ec10a-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ec10a-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ec10a-117">'T</span></span>

<span data-ttu-id="ec10a-118">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="ec10a-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec10a-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ec10a-119">See Also</span></span>

- [<span data-ttu-id="ec10a-120">Microsoft. hisse. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="ec10a-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="ec10a-121">Microsoft. hisse. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="ec10a-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="ec10a-122">Microsoft. hisse. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="ec10a-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)