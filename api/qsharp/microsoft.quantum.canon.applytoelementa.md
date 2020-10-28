---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: ApplyToElementA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: f34089c2a45de281507cb79bde8a8cb9d2fefe47
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729264"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="c1196-102">ApplyToElementA işlemi</span><span class="sxs-lookup"><span data-stu-id="c1196-102">ApplyToElementA operation</span></span>

<span data-ttu-id="c1196-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c1196-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c1196-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c1196-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c1196-105">Bir dizinin belirli bir öğesine bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="c1196-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="c1196-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c1196-106">Description</span></span>

<span data-ttu-id="c1196-107">Bir işlem `op` , dizin ve bir `index` hedef dizisi verildiğinde `targets` , geçerlidir `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="c1196-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="c1196-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="c1196-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="c1196-109">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="c1196-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="c1196-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="c1196-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="c1196-111">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1196-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1196-112">Hedef dizisine bir dizin.</span><span class="sxs-lookup"><span data-stu-id="c1196-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c1196-113">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="c1196-113">targets : 'T[]</span></span>

<span data-ttu-id="c1196-114">İçin olası hedeflerin bir dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="c1196-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c1196-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1196-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c1196-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c1196-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c1196-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c1196-117">'T</span></span>

<span data-ttu-id="c1196-118">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="c1196-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1196-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c1196-119">See Also</span></span>

- [<span data-ttu-id="c1196-120">Microsoft. hisse. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="c1196-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="c1196-121">Microsoft. hisse. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="c1196-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="c1196-122">Microsoft. hisse. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="c1196-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)