---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: ApplySeriesOfOpsC işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: 308256833dc607f685e3a5f2278e374cf3b6ce22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844641"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="0cb1e-102">ApplySeriesOfOpsC işlemi</span><span class="sxs-lookup"><span data-stu-id="0cb1e-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="0cb1e-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0cb1e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0cb1e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0cb1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0cb1e-105">Bir dizi üzerinde sırayla Ops ve hedefleri listesini uygular.</span><span class="sxs-lookup"><span data-stu-id="0cb1e-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="0cb1e-106">Tarafından</span><span class="sxs-lookup"><span data-stu-id="0cb1e-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="0cb1e-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="0cb1e-107">Input</span></span>

### <a name="listofops--t--unit--is-ctl"></a><span data-ttu-id="0cb1e-108">Lıfops: 'T [] => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL []</span><span class="sxs-lookup"><span data-stu-id="0cb1e-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="0cb1e-109">Her biri bir 'T dizisi alan Ops listesi, uygulanacak.</span><span class="sxs-lookup"><span data-stu-id="0cb1e-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="0cb1e-110">Bunlar sırasıyla, önce en düşük dizin olarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="0cb1e-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="0cb1e-111">Her birinin denetimli bir functor 'a sahip olması gerekir</span><span class="sxs-lookup"><span data-stu-id="0cb1e-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="0cb1e-112">hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="0cb1e-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="0cb1e-113">Op 'ın hedeflerini tanımlayan iç içe diziler.</span><span class="sxs-lookup"><span data-stu-id="0cb1e-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="0cb1e-114">Her dizi, kullanılacak dizinleri açıklayan bir liste içermelidir.</span><span class="sxs-lookup"><span data-stu-id="0cb1e-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="0cb1e-115">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="0cb1e-115">register : 'T[]</span></span>

<span data-ttu-id="0cb1e-116">Üzerinde işlem yapmak için qubit kaydolun.</span><span class="sxs-lookup"><span data-stu-id="0cb1e-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0cb1e-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0cb1e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0cb1e-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="0cb1e-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0cb1e-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="0cb1e-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="0cb1e-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="0cb1e-120">Example</span></span>

<span data-ttu-id="0cb1e-121">Aşağıdaki, exp ([PauliX, PauliY], 0,5) ile qubits 0, 1//ve X-qubit 2 Let Ops = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubitC (X, _)]; için geçerlidir. Let dizinleri = [[0, 1], [2]]; ApplySeriesOfOpsC (Ops, dizinler, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="0cb1e-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitC(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsC(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="0cb1e-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0cb1e-122">See Also</span></span>

- [<span data-ttu-id="0cb1e-123">Microsoft. hisse. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="0cb1e-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)