---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: fc9ba6576b56d7df1a57334e1da46b9c48376ecb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853734"
---
# <a name="mresetz-operation"></a><span data-ttu-id="7467b-102">MResetZ işlemi</span><span class="sxs-lookup"><span data-stu-id="7467b-102">MResetZ operation</span></span>

<span data-ttu-id="7467b-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="7467b-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="7467b-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7467b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7467b-105">Z tabanında tek bir qubit ölçer ve ölçüyü izleyen sabit bir başlangıç durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="7467b-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="7467b-106">Description</span><span class="sxs-lookup"><span data-stu-id="7467b-106">Description</span></span>

<span data-ttu-id="7467b-107">$Z $-temelinde tek qubit ölçümü gerçekleştirir ve ölçü sonrasında qubitin $ \ket $ ' e döndürülmesini sağlar {0} .</span><span class="sxs-lookup"><span data-stu-id="7467b-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="7467b-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="7467b-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="7467b-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7467b-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7467b-110">Ölçülecek tek bir qubit.</span><span class="sxs-lookup"><span data-stu-id="7467b-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="7467b-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="7467b-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="7467b-112">`target`Pauli $Z $ tabanında ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="7467b-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>