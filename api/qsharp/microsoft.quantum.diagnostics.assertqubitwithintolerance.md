---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Assertqubitwithıntoleransı işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 56b7f93f33ae18146c1fb13d404fc1d119eee72e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202201"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="a5e9e-102">Assertqubitwithıntoleransı işlemi</span><span class="sxs-lookup"><span data-stu-id="a5e9e-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="a5e9e-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a5e9e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a5e9e-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a5e9e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a5e9e-105">Qubit 'in `q` Pauli Z işlecinin, belirli bir toleransa kadar beklenen eigenstate olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="a5e9e-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="a5e9e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a5e9e-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="a5e9e-107">beklenen: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="a5e9e-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="a5e9e-108">Qubitin nerede olması beklenen durum: `Zero` veya `One` .</span><span class="sxs-lookup"><span data-stu-id="a5e9e-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="a5e9e-109">s: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a5e9e-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a5e9e-110">Durumu onaylanan qubit.</span><span class="sxs-lookup"><span data-stu-id="a5e9e-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="a5e9e-111">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a5e9e-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a5e9e-112">Beklenen sonucu döndüren qubit ölçüsünün toleransı.</span><span class="sxs-lookup"><span data-stu-id="a5e9e-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a5e9e-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5e9e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a5e9e-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a5e9e-114">Remarks</span></span>

<span data-ttu-id="a5e9e-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Yalnızca $Z $ eigenstates yerine rastgele qubit durumlarını ele almasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="a5e9e-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5e9e-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a5e9e-116">See Also</span></span>

- [<span data-ttu-id="a5e9e-117">Microsoft. hisse. Diagnostics. Assertqubitişsınstatewithıntoleransı</span><span class="sxs-lookup"><span data-stu-id="a5e9e-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)