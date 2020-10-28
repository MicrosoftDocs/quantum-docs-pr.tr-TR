---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: aff0bcb831960153166e88aef1f05e000125d5d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729342"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="7f0ce-102">ApplySeriesOfOps işlemi</span><span class="sxs-lookup"><span data-stu-id="7f0ce-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="7f0ce-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7f0ce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7f0ce-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7f0ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7f0ce-105">Bir dizi üzerinde sırayla Ops ve hedefleri listesini uygular.</span><span class="sxs-lookup"><span data-stu-id="7f0ce-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7f0ce-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7f0ce-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="7f0ce-107">Lıfops: 'T [] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="7f0ce-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="7f0ce-108">Her biri bir 'T dizisi alan Ops listesi, uygulanacak.</span><span class="sxs-lookup"><span data-stu-id="7f0ce-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="7f0ce-109">Bunlar sırasıyla, önce en düşük dizin olarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="7f0ce-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="7f0ce-110">hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="7f0ce-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="7f0ce-111">Op 'ın hedeflerini tanımlayan iç içe diziler.</span><span class="sxs-lookup"><span data-stu-id="7f0ce-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="7f0ce-112">Her dizi, kullanılacak dizinleri açıklayan bir liste içermelidir.</span><span class="sxs-lookup"><span data-stu-id="7f0ce-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="7f0ce-113">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="7f0ce-113">register : 'T[]</span></span>

<span data-ttu-id="7f0ce-114">Üzerinde işlem yapmak için qubit kaydolun.</span><span class="sxs-lookup"><span data-stu-id="7f0ce-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7f0ce-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7f0ce-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7f0ce-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="7f0ce-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7f0ce-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="7f0ce-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="7f0ce-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7f0ce-118">See Also</span></span>

- [<span data-ttu-id="7f0ce-119">Microsoft. hisse. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="7f0ce-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)