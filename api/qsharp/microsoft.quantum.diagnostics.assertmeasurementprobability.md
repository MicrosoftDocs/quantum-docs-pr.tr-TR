---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 2fd89121516ef6994dedb75b214589b4e360ff8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830831"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="ce2ce-102">AssertMeasurementProbability işlemi</span><span class="sxs-lookup"><span data-stu-id="ce2ce-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="ce2ce-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ce2ce-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ce2ce-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ce2ce-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ce2ce-105">Verilen Pabdtabanında verilen qubit 'leri ölçmeye yönelik onaylar, belirli bir tolerans dahilinde verilen olasılığa sahip olur.</span><span class="sxs-lookup"><span data-stu-id="ce2ce-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ce2ce-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ce2ce-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="ce2ce-107">tabanlar: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="ce2ce-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="ce2ce-108">Bir multi-qubit Pauli işleci olarak ifade edilen olasılığını onaylama için bir ölçüm etkisi.</span><span class="sxs-lookup"><span data-stu-id="ce2ce-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ce2ce-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ce2ce-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ce2ce-110">Onaylama yapılacak bir kayıt.</span><span class="sxs-lookup"><span data-stu-id="ce2ce-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="ce2ce-111">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="ce2ce-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="ce2ce-112">Beklenen sonucu `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="ce2ce-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="ce2ce-113">prob: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ce2ce-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ce2ce-114">Verilen sonucun beklenildiği olasılık.</span><span class="sxs-lookup"><span data-stu-id="ce2ce-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="ce2ce-115">Msg: [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ce2ce-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ce2ce-116">Onaylama başarısız olursa bildirilecek bir ileti.</span><span class="sxs-lookup"><span data-stu-id="ce2ce-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="ce2ce-117">tol: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ce2ce-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="ce2ce-118">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce2ce-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="ce2ce-119">Örnek</span><span class="sxs-lookup"><span data-stu-id="ce2ce-119">Example</span></span>

```qsharp
using (register = Qubit()) {
    H(register);
    AssertProb([PauliZ], [register], One, 0.5,
        "Measuring in conjugate basis did not give 50/50 results.", 1e-5);
}
```

## <a name="remarks"></a><span data-ttu-id="ce2ce-120">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ce2ce-120">Remarks</span></span>

<span data-ttu-id="ce2ce-121">Bu işlemin adjoint ve kontrollü sürümlerinin koşulu denetyacağını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="ce2ce-121">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce2ce-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ce2ce-122">See Also</span></span>

- [<span data-ttu-id="ce2ce-123">Microsoft. hisse. Diagnostics. Assertölçüm</span><span class="sxs-lookup"><span data-stu-id="ce2ce-123">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)