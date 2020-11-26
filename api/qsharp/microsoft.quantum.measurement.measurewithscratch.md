---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Measurewithkaralama işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: c42316a811e0e4a81c7f244c093a2be88fe5c733
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227072"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="d673b-102">Measurewithkaralama işlemi</span><span class="sxs-lookup"><span data-stu-id="d673b-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="d673b-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="d673b-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="d673b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d673b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d673b-105">Ölçüyü gerçekleştirmek için açık bir karalama qubit kullanarak verilen Pauli işlecini ölçer.</span><span class="sxs-lookup"><span data-stu-id="d673b-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="d673b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d673b-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="d673b-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="d673b-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="d673b-108">Tek qubit Pauli işleçleri dizisi olarak belirtilen bir multi-qubit Pauli işleci.</span><span class="sxs-lookup"><span data-stu-id="d673b-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d673b-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d673b-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d673b-110">Ölçülecek qubit kayıt.</span><span class="sxs-lookup"><span data-stu-id="d673b-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="d673b-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="d673b-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="d673b-112">Kayıttaki verilen Pauli işlecinin ölçüme sonucu `target` .</span><span class="sxs-lookup"><span data-stu-id="d673b-112">The result of measuring the given Pauli operator on the `target` register.</span></span>