---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: 052cb52d4ee6500e60043ab7f808497058924afe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844659"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="2fa85-102">ApplySeriesOfOpsA işlemi</span><span class="sxs-lookup"><span data-stu-id="2fa85-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="2fa85-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2fa85-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2fa85-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2fa85-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2fa85-105">Bir dizi üzerinde sırayla Ops ve hedefleri listesini uygular.</span><span class="sxs-lookup"><span data-stu-id="2fa85-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="2fa85-106">(Adjoint)</span><span class="sxs-lookup"><span data-stu-id="2fa85-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="2fa85-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="2fa85-107">Input</span></span>

### <a name="listofops--t--unit--is-adj"></a><span data-ttu-id="2fa85-108">Lıfops: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı []</span><span class="sxs-lookup"><span data-stu-id="2fa85-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="2fa85-109">Her biri bir 'T dizisi alan Ops listesi, uygulanacak.</span><span class="sxs-lookup"><span data-stu-id="2fa85-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="2fa85-110">Bunlar sırasıyla, önce en düşük dizin olarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="2fa85-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="2fa85-111">Her birinin bir adjoint functor 'ı olmalıdır</span><span class="sxs-lookup"><span data-stu-id="2fa85-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="2fa85-112">hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="2fa85-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="2fa85-113">Op 'ın hedeflerini tanımlayan iç içe diziler.</span><span class="sxs-lookup"><span data-stu-id="2fa85-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="2fa85-114">Her dizi, kullanılacak dizinleri açıklayan bir liste içermelidir.</span><span class="sxs-lookup"><span data-stu-id="2fa85-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="2fa85-115">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="2fa85-115">register : 'T[]</span></span>

<span data-ttu-id="2fa85-116">Üzerinde işlem yapmak için qubit kaydolun.</span><span class="sxs-lookup"><span data-stu-id="2fa85-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2fa85-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2fa85-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2fa85-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2fa85-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2fa85-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="2fa85-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="2fa85-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="2fa85-120">Example</span></span>

<span data-ttu-id="2fa85-121">Aşağıdaki, exp ([PauliX, PauliY], 0,5) ile qubits 0, 1//ve X-qubit 2 Let Ops = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubitA (X, _)]; için geçerlidir. Let dizinleri = [[0, 1], [2]]; ApplySeriesOfOpsA (Ops, dizinler, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="2fa85-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitA(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsA(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="2fa85-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2fa85-122">See Also</span></span>

- [<span data-ttu-id="2fa85-123">Microsoft. hisse. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="2fa85-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)