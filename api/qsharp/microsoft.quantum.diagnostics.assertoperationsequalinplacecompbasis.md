---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: AssertOperationsEqualInPlaceCompBasis işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: 3275680f86ca2a178c7f044b97d226fe41c3186c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727326"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a><span data-ttu-id="b2509-102">AssertOperationsEqualInPlaceCompBasis işlemi</span><span class="sxs-lookup"><span data-stu-id="b2509-102">AssertOperationsEqualInPlaceCompBasis operation</span></span>

<span data-ttu-id="b2509-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b2509-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b2509-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2509-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2509-105">İşlemin `givenU` `expectedU` yalnızca işlem temelinde vektörlerdeki işlem eylemlerini denetleyerek verilen giriş boyutundaki işleme eşit olup olmadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="b2509-105">Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis.</span></span>
<span data-ttu-id="b2509-106">Bu, iki unitı 'nin eşitliğine yönelik gerekli, ancak yeterli olmayan bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="b2509-106">This is a necessary, but not sufficient, condition for the equality of two unitaries.</span></span>

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="b2509-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="b2509-107">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="b2509-108">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b2509-108">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b2509-109">İşlemler `givenU` ve üzerinde çalışan qubits $n $ sayısı `expectedU` .</span><span class="sxs-lookup"><span data-stu-id="b2509-109">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="b2509-110">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2509-110">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b2509-111">$N $ qubits üzerinde işlem denetlenecek.</span><span class="sxs-lookup"><span data-stu-id="b2509-111">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="b2509-112">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama</span><span class="sxs-lookup"><span data-stu-id="b2509-112">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="b2509-113">İle Karşılaştırılacak $n $ qubit üzerinde başvuru işlemi `givenU` .</span><span class="sxs-lookup"><span data-stu-id="b2509-113">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2509-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2509-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

