---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727319"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="07c49-102">AssertQubit işlemi</span><span class="sxs-lookup"><span data-stu-id="07c49-102">AssertQubit operation</span></span>

<span data-ttu-id="07c49-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="07c49-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="07c49-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07c49-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07c49-105">Qubitin `q` Pauli Z işlecinin beklenen eigenstate öğesinde olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="07c49-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="07c49-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="07c49-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="07c49-107">beklenen: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="07c49-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="07c49-108">Qubitin nerede olması beklenen durum: `Zero` veya `One` .</span><span class="sxs-lookup"><span data-stu-id="07c49-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="07c49-109">s: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="07c49-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="07c49-110">Durumu onaylanan qubit.</span><span class="sxs-lookup"><span data-stu-id="07c49-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="07c49-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07c49-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="07c49-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="07c49-112">Remarks</span></span>

<span data-ttu-id="07c49-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Yalnızca $Z $ eigenstates yerine rastgele qubit durumlarını ele almasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="07c49-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="07c49-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="07c49-114">See Also</span></span>

- [<span data-ttu-id="07c49-115">Microsoft. hisse. Diagnostics. Assertqubitişsınstatewithıntoleransı</span><span class="sxs-lookup"><span data-stu-id="07c49-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)