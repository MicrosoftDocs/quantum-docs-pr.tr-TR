---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: ApplyToHeadA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3397c059706c48ff8ca47dd2312cfa9565aacaba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208644"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="c07ea-102">ApplyToHeadA işlemi</span><span class="sxs-lookup"><span data-stu-id="c07ea-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="c07ea-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c07ea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c07ea-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c07ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c07ea-105">Bir işlemi bir dizinin ilk öğesine uygular.</span><span class="sxs-lookup"><span data-stu-id="c07ea-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="c07ea-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c07ea-106">Description</span></span>

<span data-ttu-id="c07ea-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="c07ea-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c07ea-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="c07ea-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="c07ea-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="c07ea-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c07ea-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="c07ea-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c07ea-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="c07ea-111">targets : 'T[]</span></span>

<span data-ttu-id="c07ea-112">İlki uygulanacak bir dizi hedef `op` .</span><span class="sxs-lookup"><span data-stu-id="c07ea-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c07ea-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c07ea-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c07ea-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c07ea-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c07ea-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c07ea-115">'T</span></span>

<span data-ttu-id="c07ea-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="c07ea-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c07ea-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c07ea-117">See Also</span></span>

- [<span data-ttu-id="c07ea-118">Microsoft. hisse. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="c07ea-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="c07ea-119">Microsoft. hisse. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="c07ea-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="c07ea-120">Microsoft. hisse. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="c07ea-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)