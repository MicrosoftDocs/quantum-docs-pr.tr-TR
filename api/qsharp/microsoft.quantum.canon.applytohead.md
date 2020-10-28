---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e5fc439f48a5c7e527b7805c35cce18eca3ab36
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729173"
---
# <a name="applytohead-operation"></a><span data-ttu-id="40b5b-102">ApplyToHead işlemi</span><span class="sxs-lookup"><span data-stu-id="40b5b-102">ApplyToHead operation</span></span>

<span data-ttu-id="40b5b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="40b5b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="40b5b-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="40b5b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="40b5b-105">Bir işlemi bir dizinin ilk öğesine uygular.</span><span class="sxs-lookup"><span data-stu-id="40b5b-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="40b5b-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="40b5b-106">Description</span></span>

<span data-ttu-id="40b5b-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="40b5b-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="40b5b-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="40b5b-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="40b5b-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40b5b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="40b5b-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="40b5b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="40b5b-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="40b5b-111">targets : 'T[]</span></span>

<span data-ttu-id="40b5b-112">İlki uygulanacak bir dizi hedef `op` .</span><span class="sxs-lookup"><span data-stu-id="40b5b-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="40b5b-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40b5b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="40b5b-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="40b5b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="40b5b-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="40b5b-115">'T</span></span>

<span data-ttu-id="40b5b-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="40b5b-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="40b5b-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="40b5b-117">See Also</span></span>

- [<span data-ttu-id="40b5b-118">Microsoft. hisse. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="40b5b-118">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="40b5b-119">Microsoft. hisse. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="40b5b-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="40b5b-120">Microsoft. hisse. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="40b5b-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)