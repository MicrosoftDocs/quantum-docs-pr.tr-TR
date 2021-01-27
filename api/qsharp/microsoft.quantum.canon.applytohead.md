---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841330"
---
# <a name="applytohead-operation"></a><span data-ttu-id="f0c6e-102">ApplyToHead işlemi</span><span class="sxs-lookup"><span data-stu-id="f0c6e-102">ApplyToHead operation</span></span>

<span data-ttu-id="f0c6e-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f0c6e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f0c6e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0c6e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0c6e-105">Bir işlemi bir dizinin ilk öğesine uygular.</span><span class="sxs-lookup"><span data-stu-id="f0c6e-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="f0c6e-106">Description</span><span class="sxs-lookup"><span data-stu-id="f0c6e-106">Description</span></span>

<span data-ttu-id="f0c6e-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="f0c6e-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="f0c6e-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="f0c6e-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="f0c6e-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f0c6e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f0c6e-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="f0c6e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="f0c6e-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="f0c6e-111">targets : 'T[]</span></span>

<span data-ttu-id="f0c6e-112">İlki uygulanacak bir dizi hedef `op` .</span><span class="sxs-lookup"><span data-stu-id="f0c6e-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f0c6e-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f0c6e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f0c6e-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f0c6e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f0c6e-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f0c6e-115">'T</span></span>

<span data-ttu-id="f0c6e-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="f0c6e-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="f0c6e-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="f0c6e-117">Example</span></span>

<span data-ttu-id="f0c6e-118">Aşağıdaki Q # parçacıkları eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="f0c6e-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a><span data-ttu-id="f0c6e-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f0c6e-119">See Also</span></span>

- [<span data-ttu-id="f0c6e-120">Microsoft. hisse. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="f0c6e-120">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="f0c6e-121">Microsoft. hisse. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="f0c6e-121">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="f0c6e-122">Microsoft. hisse. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="f0c6e-122">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)