---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: ApplyToElement işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8cbc42a1c43b4c9a037729671eb3c82d365af580
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217637"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="255a6-102">ApplyToElement işlemi</span><span class="sxs-lookup"><span data-stu-id="255a6-102">ApplyToElement operation</span></span>

<span data-ttu-id="255a6-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="255a6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="255a6-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="255a6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="255a6-105">Bir dizinin belirli bir öğesine bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="255a6-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="255a6-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="255a6-106">Description</span></span>

<span data-ttu-id="255a6-107">Bir işlem `op` , dizin ve bir `index` hedef dizisi verildiğinde `targets` , geçerlidir `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="255a6-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="255a6-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="255a6-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="255a6-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="255a6-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="255a6-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="255a6-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="255a6-111">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="255a6-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="255a6-112">Hedef dizisine bir dizin.</span><span class="sxs-lookup"><span data-stu-id="255a6-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="255a6-113">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="255a6-113">targets : 'T[]</span></span>

<span data-ttu-id="255a6-114">İçin olası hedeflerin bir dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="255a6-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="255a6-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="255a6-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="255a6-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="255a6-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="255a6-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="255a6-117">'T</span></span>

<span data-ttu-id="255a6-118">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="255a6-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="255a6-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="255a6-119">See Also</span></span>

- [<span data-ttu-id="255a6-120">Microsoft. hisse. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="255a6-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="255a6-121">Microsoft. hisse. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="255a6-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="255a6-122">Microsoft. hisse. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="255a6-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)