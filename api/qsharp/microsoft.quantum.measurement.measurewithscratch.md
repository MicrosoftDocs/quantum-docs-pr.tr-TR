---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Measurewithkaralama işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730986"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="2fad8-102">Measurewithkaralama işlemi</span><span class="sxs-lookup"><span data-stu-id="2fad8-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="2fad8-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="2fad8-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="2fad8-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2fad8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2fad8-105">Ölçüyü gerçekleştirmek için açık bir karalama qubit kullanarak verilen Pauli işlecini ölçer.</span><span class="sxs-lookup"><span data-stu-id="2fad8-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="2fad8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2fad8-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="2fad8-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="2fad8-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="2fad8-108">Tek qubit Pauli işleçleri dizisi olarak belirtilen bir multi-qubit Pauli işleci.</span><span class="sxs-lookup"><span data-stu-id="2fad8-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2fad8-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2fad8-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2fad8-110">Ölçülecek qubit kayıt.</span><span class="sxs-lookup"><span data-stu-id="2fad8-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="2fad8-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="2fad8-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="2fad8-112">Kayıttaki verilen Pauli işlecinin ölçüme sonucu `target` .</span><span class="sxs-lookup"><span data-stu-id="2fad8-112">The result of measuring the given Pauli operator on the `target` register.</span></span>