---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b8810e7d31689046e72905195a3a25ef80fc8d67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218011"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="c9f3f-102">ApplySeriesOfOps işlemi</span><span class="sxs-lookup"><span data-stu-id="c9f3f-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="c9f3f-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c9f3f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c9f3f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9f3f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9f3f-105">Bir dizi üzerinde sırayla Ops ve hedefleri listesini uygular.</span><span class="sxs-lookup"><span data-stu-id="c9f3f-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c9f3f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c9f3f-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="c9f3f-107">Lıfops: 'T [] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="c9f3f-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="c9f3f-108">Her biri bir 'T dizisi alan Ops listesi, uygulanacak.</span><span class="sxs-lookup"><span data-stu-id="c9f3f-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="c9f3f-109">Bunlar sırasıyla, önce en düşük dizin olarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="c9f3f-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="c9f3f-110">hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="c9f3f-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="c9f3f-111">Op 'ın hedeflerini tanımlayan iç içe diziler.</span><span class="sxs-lookup"><span data-stu-id="c9f3f-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="c9f3f-112">Her dizi, kullanılacak dizinleri açıklayan bir liste içermelidir.</span><span class="sxs-lookup"><span data-stu-id="c9f3f-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="c9f3f-113">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="c9f3f-113">register : 'T[]</span></span>

<span data-ttu-id="c9f3f-114">Üzerinde işlem yapmak için qubit kaydolun.</span><span class="sxs-lookup"><span data-stu-id="c9f3f-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c9f3f-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c9f3f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c9f3f-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c9f3f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c9f3f-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c9f3f-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="c9f3f-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c9f3f-118">See Also</span></span>

- [<span data-ttu-id="c9f3f-119">Microsoft. hisse. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="c9f3f-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)