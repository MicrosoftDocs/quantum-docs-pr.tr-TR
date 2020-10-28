---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 7348ab3941af391c451d5c66f888cf3b6662cf20
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730999"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="8c137-102">MeasurePaulis işlemi</span><span class="sxs-lookup"><span data-stu-id="8c137-102">MeasurePaulis operation</span></span>

<span data-ttu-id="8c137-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="8c137-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="8c137-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8c137-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8c137-105">Multi-qubitpauli işleçleri dizisi verildiğinde, her birini belirtilen ölçüm aracını kullanarak ölçer ve sonra sonuçların dizisini döndürür.</span><span class="sxs-lookup"><span data-stu-id="8c137-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="8c137-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8c137-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="8c137-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="8c137-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="8c137-108">Ölçülecek Multi-qubit Pauli işleçleri dizisi.</span><span class="sxs-lookup"><span data-stu-id="8c137-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8c137-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8c137-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8c137-110">Verilen operatörlerin ölçülmesi için kaydolun.</span><span class="sxs-lookup"><span data-stu-id="8c137-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="8c137-111">Araç: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="8c137-111">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="8c137-112">Verilen bir multi-qubit işlecinin ölçüsünü gerçekleştiren işlem.</span><span class="sxs-lookup"><span data-stu-id="8c137-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="8c137-113">Çıkış: __geçersiz <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="8c137-113">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="8c137-114">Her öğesinin ' de bir öğelerinin ölçüden elde edilen sonuçları dizisi `paulis` `target` .</span><span class="sxs-lookup"><span data-stu-id="8c137-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>