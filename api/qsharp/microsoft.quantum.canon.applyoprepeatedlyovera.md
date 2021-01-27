---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverA
title: ApplyOpRepeatedlyOverA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 30e91d8a0292c7389ad83f14e1b7d4a8248cbb96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841617"
---
# <a name="applyoprepeatedlyovera-operation"></a><span data-ttu-id="9262e-102">ApplyOpRepeatedlyOverA işlemi</span><span class="sxs-lookup"><span data-stu-id="9262e-102">ApplyOpRepeatedlyOverA operation</span></span>

<span data-ttu-id="9262e-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9262e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9262e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9262e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9262e-105">Aynı op 'yi bir qubit kayıt için birden çok kez uygular.</span><span class="sxs-lookup"><span data-stu-id="9262e-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverA (op : (Qubit[] => Unit is Adj), targets : Int[][], register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="9262e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9262e-106">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="9262e-107">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="9262e-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9262e-108">Qubit kaydına birden çok kez uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="9262e-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="9262e-109">hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="9262e-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="9262e-110">Op 'ın hedeflerini tanımlayan iç içe diziler.</span><span class="sxs-lookup"><span data-stu-id="9262e-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="9262e-111">Her dizi, kullanılacak qubits 'i açıklayan bir liste içermelidir.</span><span class="sxs-lookup"><span data-stu-id="9262e-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="9262e-112">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9262e-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9262e-113">Üzerinde işlem yapmak için qubit kaydolun.</span><span class="sxs-lookup"><span data-stu-id="9262e-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9262e-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9262e-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9262e-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9262e-115">See Also</span></span>

- [<span data-ttu-id="9262e-116">Microsoft. hisse. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="9262e-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)