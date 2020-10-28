---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: a16d7405388b560edcdb6c36b6668791f7ba1398
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733791"
---
# <a name="mresetx-operation"></a><span data-ttu-id="eaedb-102">MResetX işlemi</span><span class="sxs-lookup"><span data-stu-id="eaedb-102">MResetX operation</span></span>

<span data-ttu-id="eaedb-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="eaedb-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="eaedb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eaedb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eaedb-105">X temelinde tek bir qubit ölçer ve ölçüyü izleyen sabit bir başlangıç durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="eaedb-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="eaedb-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="eaedb-106">Description</span></span>

<span data-ttu-id="eaedb-107">$X $-temelinde tek qubit ölçümü gerçekleştirir ve ölçü sonrasında qubitin $ \ket $ ' e döndürülmesini sağlar {0} .</span><span class="sxs-lookup"><span data-stu-id="eaedb-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="eaedb-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="eaedb-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="eaedb-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="eaedb-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="eaedb-110">Ölçülecek tek bir qubit.</span><span class="sxs-lookup"><span data-stu-id="eaedb-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="eaedb-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="eaedb-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="eaedb-112">`target`Pauli $X $ tabanında ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="eaedb-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>