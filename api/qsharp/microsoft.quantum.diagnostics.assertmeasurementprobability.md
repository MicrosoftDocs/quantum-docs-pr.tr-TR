---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 032b9224ad728f0637596668c2928a889deeba55
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202371"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="9e95d-102">AssertMeasurementProbability işlemi</span><span class="sxs-lookup"><span data-stu-id="9e95d-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="9e95d-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9e95d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9e95d-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9e95d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9e95d-105">Verilen Pabdtabanında verilen qubit 'leri ölçmeye yönelik onaylar, belirli bir tolerans dahilinde verilen olasılığa sahip olur.</span><span class="sxs-lookup"><span data-stu-id="9e95d-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9e95d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9e95d-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="9e95d-107">tabanlar: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="9e95d-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="9e95d-108">Bir multi-qubit Pauli işleci olarak ifade edilen olasılığını onaylama için bir ölçüm etkisi.</span><span class="sxs-lookup"><span data-stu-id="9e95d-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="9e95d-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9e95d-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9e95d-110">Onaylama yapılacak bir kayıt.</span><span class="sxs-lookup"><span data-stu-id="9e95d-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="9e95d-111">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="9e95d-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="9e95d-112">Beklenen sonucu `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="9e95d-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="9e95d-113">prob: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9e95d-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9e95d-114">Verilen sonucun beklenildiği olasılık.</span><span class="sxs-lookup"><span data-stu-id="9e95d-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="9e95d-115">Msg: [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9e95d-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9e95d-116">Onaylama başarısız olursa bildirilecek bir ileti.</span><span class="sxs-lookup"><span data-stu-id="9e95d-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="9e95d-117">tol: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9e95d-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="9e95d-118">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e95d-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9e95d-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9e95d-119">Remarks</span></span>

<span data-ttu-id="9e95d-120">Bu işlemin adjoint ve kontrollü sürümlerinin koşulu denetyacağını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="9e95d-120">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e95d-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9e95d-121">See Also</span></span>

- [<span data-ttu-id="9e95d-122">Microsoft. hisse. Diagnostics. Assertölçüm</span><span class="sxs-lookup"><span data-stu-id="9e95d-122">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)