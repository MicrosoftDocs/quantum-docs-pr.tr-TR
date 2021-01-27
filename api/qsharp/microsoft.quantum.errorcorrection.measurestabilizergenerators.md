---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: d7c8df079e49b2ce0a5106e430ef4060df85cdc4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825766"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="ff428-102">MeasureStabilizerGenerators işlemi</span><span class="sxs-lookup"><span data-stu-id="ff428-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="ff428-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ff428-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ff428-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ff428-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ff428-105">Bir sabitleyici grubun verilen Oluşturucu kümesini ölçer.</span><span class="sxs-lookup"><span data-stu-id="ff428-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="ff428-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ff428-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="ff428-107">Sabitde Izergrubu: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="ff428-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="ff428-108">Multiqubit Pauli işleçleri dizisi.</span><span class="sxs-lookup"><span data-stu-id="ff428-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="ff428-109">Örneğin, `stabilizerGroup[0]` bir sabitleyici Oluşturucu olan Tensor ürünü olan tek qubit Pauli matrislerinin bir listesidir.</span><span class="sxs-lookup"><span data-stu-id="ff428-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="ff428-110">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="ff428-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="ff428-111">Sabitleyici kodun tanımlandığı bir qubits dizisi.</span><span class="sxs-lookup"><span data-stu-id="ff428-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="ff428-112">Araç: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="ff428-112">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="ff428-113">Multiqubit Pauli işlecinin nasıl ölçülmesi gerektiğini belirten bir işlem.</span><span class="sxs-lookup"><span data-stu-id="ff428-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="ff428-114">Çıkış: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="ff428-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="ff428-115">Ölçümlerin sonucu.</span><span class="sxs-lookup"><span data-stu-id="ff428-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff428-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ff428-116">Remarks</span></span>

<span data-ttu-id="ff428-117">Bu, verilen bir dizi kümesinin yürütülüyor olup olmadığını denetlemez.</span><span class="sxs-lookup"><span data-stu-id="ff428-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="ff428-118">Bunlar işlem yapılmadığından, ölçümlerin sonucu rastgele olabilir.</span><span class="sxs-lookup"><span data-stu-id="ff428-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>