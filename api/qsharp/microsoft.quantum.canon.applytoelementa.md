---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: ApplyToElementA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 57d870c7fbd099212b13f75bd85e57c046280d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850759"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="288ea-102">ApplyToElementA işlemi</span><span class="sxs-lookup"><span data-stu-id="288ea-102">ApplyToElementA operation</span></span>

<span data-ttu-id="288ea-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="288ea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="288ea-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="288ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="288ea-105">Bir dizinin belirli bir öğesine bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="288ea-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="288ea-106">Description</span><span class="sxs-lookup"><span data-stu-id="288ea-106">Description</span></span>

<span data-ttu-id="288ea-107">Bir işlem `op` , dizin ve bir `index` hedef dizisi verildiğinde `targets` , geçerlidir `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="288ea-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="288ea-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="288ea-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="288ea-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="288ea-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="288ea-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="288ea-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="288ea-111">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="288ea-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="288ea-112">Hedef dizisine bir dizin.</span><span class="sxs-lookup"><span data-stu-id="288ea-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="288ea-113">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="288ea-113">targets : 'T[]</span></span>

<span data-ttu-id="288ea-114">İçin olası hedeflerin bir dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="288ea-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="288ea-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="288ea-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="288ea-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="288ea-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="288ea-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="288ea-117">'T</span></span>

<span data-ttu-id="288ea-118">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="288ea-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="288ea-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="288ea-119">See Also</span></span>

- [<span data-ttu-id="288ea-120">Microsoft. hisse. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="288ea-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="288ea-121">Microsoft. hisse. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="288ea-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="288ea-122">Microsoft. hisse. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="288ea-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)