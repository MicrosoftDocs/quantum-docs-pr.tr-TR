---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9dd1343b3ebcc75592441f150eee822cfe83f9a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217892"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="76dca-102">ApplySeriesOfOpsCA işlemi</span><span class="sxs-lookup"><span data-stu-id="76dca-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="76dca-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="76dca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="76dca-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76dca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76dca-105">Bir dizi üzerinde sırayla Ops ve hedefleri listesini uygular.</span><span class="sxs-lookup"><span data-stu-id="76dca-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="76dca-106">(Adjoint + denetimli)</span><span class="sxs-lookup"><span data-stu-id="76dca-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="76dca-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="76dca-107">Input</span></span>

### <a name="listofops--t--unit--is-adj--ctl"></a><span data-ttu-id="76dca-108">Lıfops: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL []</span><span class="sxs-lookup"><span data-stu-id="76dca-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="76dca-109">Her biri bir 'T dizisi alan Ops listesi, uygulanacak.</span><span class="sxs-lookup"><span data-stu-id="76dca-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="76dca-110">Bunlar sırasıyla, önce en düşük dizin olarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="76dca-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="76dca-111">Her birinin hem adjoint hem de denetimli bir functor 'a sahip olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="76dca-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="76dca-112">hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="76dca-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="76dca-113">Op 'ın hedeflerini tanımlayan iç içe diziler.</span><span class="sxs-lookup"><span data-stu-id="76dca-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="76dca-114">Her dizi, kullanılacak dizinleri açıklayan bir liste içermelidir.</span><span class="sxs-lookup"><span data-stu-id="76dca-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="76dca-115">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="76dca-115">register : 'T[]</span></span>

<span data-ttu-id="76dca-116">Üzerinde işlem yapmak için qubit kaydolun.</span><span class="sxs-lookup"><span data-stu-id="76dca-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76dca-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76dca-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="76dca-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="76dca-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="76dca-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="76dca-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="76dca-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="76dca-120">See Also</span></span>

- [<span data-ttu-id="76dca-121">Microsoft. hisse. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="76dca-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)