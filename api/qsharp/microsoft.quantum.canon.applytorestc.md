---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: ApplyToRestC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 779c3831b2027a58f97dae9609e96d4d98247da7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208202"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="2690c-102">ApplyToRestC işlemi</span><span class="sxs-lookup"><span data-stu-id="2690c-102">ApplyToRestC operation</span></span>

<span data-ttu-id="2690c-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2690c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2690c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2690c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2690c-105">Bir işlemi, bir dizinin ilk öğesi hariç tümüne uygular.</span><span class="sxs-lookup"><span data-stu-id="2690c-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="2690c-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2690c-106">Description</span></span>

<span data-ttu-id="2690c-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="2690c-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="2690c-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="2690c-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="2690c-109">Op: 'T [] => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="2690c-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="2690c-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="2690c-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="2690c-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="2690c-111">targets : 'T[]</span></span>

<span data-ttu-id="2690c-112">Birincisi, ancak ilki uygulanacak bir dizi hedefi `op` .</span><span class="sxs-lookup"><span data-stu-id="2690c-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2690c-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2690c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2690c-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2690c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2690c-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="2690c-115">'T</span></span>

<span data-ttu-id="2690c-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="2690c-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2690c-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2690c-117">See Also</span></span>

- [<span data-ttu-id="2690c-118">Microsoft. hisse. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="2690c-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="2690c-119">Microsoft. hisse. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="2690c-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="2690c-120">Microsoft. hisse. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="2690c-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)