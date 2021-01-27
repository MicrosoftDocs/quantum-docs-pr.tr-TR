---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841508"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="15ee2-102">ApplySeriesOfOps işlemi</span><span class="sxs-lookup"><span data-stu-id="15ee2-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="15ee2-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="15ee2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="15ee2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="15ee2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="15ee2-105">Bir dizi üzerinde sırayla Ops ve hedefleri listesini uygular.</span><span class="sxs-lookup"><span data-stu-id="15ee2-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="15ee2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="15ee2-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="15ee2-107">Lıfops: 'T [] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="15ee2-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="15ee2-108">Her biri bir 'T dizisi alan Ops listesi, uygulanacak.</span><span class="sxs-lookup"><span data-stu-id="15ee2-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="15ee2-109">Bunlar sırasıyla, önce en düşük dizin olarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="15ee2-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="15ee2-110">hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="15ee2-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="15ee2-111">Op 'ın hedeflerini tanımlayan iç içe diziler.</span><span class="sxs-lookup"><span data-stu-id="15ee2-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="15ee2-112">Her dizi, kullanılacak dizinleri açıklayan bir liste içermelidir.</span><span class="sxs-lookup"><span data-stu-id="15ee2-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="15ee2-113">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="15ee2-113">register : 'T[]</span></span>

<span data-ttu-id="15ee2-114">Üzerinde işlem yapmak için qubit kaydolun.</span><span class="sxs-lookup"><span data-stu-id="15ee2-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="15ee2-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15ee2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="15ee2-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="15ee2-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="15ee2-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="15ee2-117">'T</span></span>



## <a name="example"></a><span data-ttu-id="15ee2-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="15ee2-118">Example</span></span>

<span data-ttu-id="15ee2-119">Aşağıdakiler, exp ([PauliX, PauliY], 0,5) ile qubits 0, 1//then X-qubit 2 Let Ops = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubit (X, _)]; için geçerlidir. Let dizinleri = [[0, 1], [2]]; ApplySeriesOfOps (Ops, dizinler, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="15ee2-119">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubit(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOps(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="15ee2-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="15ee2-120">See Also</span></span>

- [<span data-ttu-id="15ee2-121">Microsoft. hisse. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="15ee2-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)