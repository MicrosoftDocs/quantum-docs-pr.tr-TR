---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverCA
title: ApplyOpRepeatedlyOverCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverCA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: b7d401f323d7affc27697744bb659c687e252682
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209120"
---
# <a name="applyoprepeatedlyoverca-operation"></a><span data-ttu-id="fa094-102">ApplyOpRepeatedlyOverCA işlemi</span><span class="sxs-lookup"><span data-stu-id="fa094-102">ApplyOpRepeatedlyOverCA operation</span></span>

<span data-ttu-id="fa094-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fa094-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fa094-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa094-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa094-105">Aynı op 'yi bir qubit kayıt için birden çok kez uygular.</span><span class="sxs-lookup"><span data-stu-id="fa094-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverCA (op : (Qubit[] => Unit is Adj + Ctl), targets : Int[][], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fa094-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="fa094-106">Input</span></span>

### <a name="op--qubit--unit--is-adj--ctl"></a><span data-ttu-id="fa094-107">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="fa094-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="fa094-108">Qubit kaydına birden çok kez uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="fa094-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="fa094-109">hedefler: [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="fa094-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="fa094-110">Op 'ın hedeflerini tanımlayan iç içe diziler.</span><span class="sxs-lookup"><span data-stu-id="fa094-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="fa094-111">Her dizi, kullanılacak qubits 'i açıklayan bir liste içermelidir.</span><span class="sxs-lookup"><span data-stu-id="fa094-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="fa094-112">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fa094-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fa094-113">Üzerinde işlem yapmak için qubit kaydolun.</span><span class="sxs-lookup"><span data-stu-id="fa094-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fa094-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fa094-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="fa094-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fa094-115">See Also</span></span>

- [<span data-ttu-id="fa094-116">Microsoft. hisse. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="fa094-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)