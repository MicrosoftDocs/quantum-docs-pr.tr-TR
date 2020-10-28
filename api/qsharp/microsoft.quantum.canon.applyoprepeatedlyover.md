---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver
title: ApplyOpRepeatedlyOver işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOver
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 09f54be33a7b5c58a317a949290f5cd6d54fe841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729420"
---
# <a name="applyoprepeatedlyover-operation"></a><span data-ttu-id="32c73-102">ApplyOpRepeatedlyOver işlemi</span><span class="sxs-lookup"><span data-stu-id="32c73-102">ApplyOpRepeatedlyOver operation</span></span>

<span data-ttu-id="32c73-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="32c73-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="32c73-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="32c73-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="32c73-105">Aynı op 'yi bir qubit kayıt için birden çok kez uygular.</span><span class="sxs-lookup"><span data-stu-id="32c73-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOver (op : (Qubit[] => Unit), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="32c73-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="32c73-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="32c73-107">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="32c73-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="32c73-108">Qubit kaydına birden çok kez uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="32c73-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="32c73-109">hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="32c73-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="32c73-110">Op 'ın hedeflerini tanımlayan iç içe diziler.</span><span class="sxs-lookup"><span data-stu-id="32c73-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="32c73-111">Her dizi, kullanılacak qubits 'i açıklayan bir liste içermelidir.</span><span class="sxs-lookup"><span data-stu-id="32c73-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="32c73-112">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="32c73-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="32c73-113">Üzerinde işlem yapmak için qubit kaydolun.</span><span class="sxs-lookup"><span data-stu-id="32c73-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="32c73-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="32c73-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="32c73-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="32c73-115">See Also</span></span>

- [<span data-ttu-id="32c73-116">Microsoft. hisse. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="32c73-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)