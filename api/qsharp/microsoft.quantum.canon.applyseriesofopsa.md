---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e2b928fa4c9446e16d2bf5e7b68a32d4bba3a528
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729336"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="b72ec-102">ApplySeriesOfOpsA işlemi</span><span class="sxs-lookup"><span data-stu-id="b72ec-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="b72ec-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b72ec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b72ec-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b72ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b72ec-105">Bir dizi üzerinde sırayla Ops ve hedefleri listesini uygular.</span><span class="sxs-lookup"><span data-stu-id="b72ec-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="b72ec-106">(Adjoint)</span><span class="sxs-lookup"><span data-stu-id="b72ec-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b72ec-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="b72ec-107">Input</span></span>

### <a name="listofops--t--unit-adj"></a><span data-ttu-id="b72ec-108">Lıfops: 'T [] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması []</span><span class="sxs-lookup"><span data-stu-id="b72ec-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="b72ec-109">Her biri bir 'T dizisi alan Ops listesi, uygulanacak.</span><span class="sxs-lookup"><span data-stu-id="b72ec-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="b72ec-110">Bunlar sırasıyla, önce en düşük dizin olarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="b72ec-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="b72ec-111">Her birinin bir adjoint functor 'ı olmalıdır</span><span class="sxs-lookup"><span data-stu-id="b72ec-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="b72ec-112">hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="b72ec-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="b72ec-113">Op 'ın hedeflerini tanımlayan iç içe diziler.</span><span class="sxs-lookup"><span data-stu-id="b72ec-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="b72ec-114">Her dizi, kullanılacak dizinleri açıklayan bir liste içermelidir.</span><span class="sxs-lookup"><span data-stu-id="b72ec-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="b72ec-115">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="b72ec-115">register : 'T[]</span></span>

<span data-ttu-id="b72ec-116">Üzerinde işlem yapmak için qubit kaydolun.</span><span class="sxs-lookup"><span data-stu-id="b72ec-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b72ec-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b72ec-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b72ec-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="b72ec-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b72ec-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="b72ec-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="b72ec-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b72ec-120">See Also</span></span>

- [<span data-ttu-id="b72ec-121">Microsoft. hisse. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="b72ec-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)