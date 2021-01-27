---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Measurewithkaralama işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 4173aa9daac08a3febdfcbf12dc236f797685436
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854653"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="e0044-102">Measurewithkaralama işlemi</span><span class="sxs-lookup"><span data-stu-id="e0044-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="e0044-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="e0044-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="e0044-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0044-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0044-105">Ölçüyü gerçekleştirmek için açık bir karalama qubit kullanarak verilen Pauli işlecini ölçer.</span><span class="sxs-lookup"><span data-stu-id="e0044-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="e0044-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e0044-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="e0044-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="e0044-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="e0044-108">Tek qubit Pauli işleçleri dizisi olarak belirtilen bir multi-qubit Pauli işleci.</span><span class="sxs-lookup"><span data-stu-id="e0044-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e0044-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e0044-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e0044-110">Ölçülecek qubit kayıt.</span><span class="sxs-lookup"><span data-stu-id="e0044-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="e0044-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="e0044-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="e0044-112">Kayıttaki verilen Pauli işlecinin ölçüme sonucu `target` .</span><span class="sxs-lookup"><span data-stu-id="e0044-112">The result of measuring the given Pauli operator on the `target` register.</span></span>