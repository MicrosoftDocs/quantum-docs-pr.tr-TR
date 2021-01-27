---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Assertölçüm işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 8f5113f1d6b8e4f104af10ca330e244e95793418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853497"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="5c91c-102">Assertölçüm işlemi</span><span class="sxs-lookup"><span data-stu-id="5c91c-102">AssertMeasurement operation</span></span>

<span data-ttu-id="5c91c-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5c91c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5c91c-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5c91c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5c91c-105">Verilen Pauli tabanında verilen qubits ölçmeye yönelik onaylar, her zaman verilen sonuca sahip olur.</span><span class="sxs-lookup"><span data-stu-id="5c91c-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5c91c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5c91c-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="5c91c-107">tabanlar: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="5c91c-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="5c91c-108">Bir multi-qubit Pauli işleci olarak ifade edilen olasılığını onaylama için bir ölçüm etkisi.</span><span class="sxs-lookup"><span data-stu-id="5c91c-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5c91c-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5c91c-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5c91c-110">Onaylama yapılacak bir kayıt.</span><span class="sxs-lookup"><span data-stu-id="5c91c-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="5c91c-111">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="5c91c-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="5c91c-112">Beklenen sonucu `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="5c91c-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="5c91c-113">Msg: [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="5c91c-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="5c91c-114">Onaylama başarısız olursa bildirilecek bir ileti.</span><span class="sxs-lookup"><span data-stu-id="5c91c-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5c91c-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c91c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5c91c-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5c91c-116">Remarks</span></span>

<span data-ttu-id="5c91c-117">Bu işlemin adjoint ve kontrollü sürümlerinin koşulu denetyacağını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="5c91c-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c91c-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5c91c-118">See Also</span></span>

- [<span data-ttu-id="5c91c-119">Microsoft. hisse. tanılama. AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="5c91c-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)