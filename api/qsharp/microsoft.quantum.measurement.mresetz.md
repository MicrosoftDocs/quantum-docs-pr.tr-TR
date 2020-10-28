---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726509"
---
# <a name="mresetz-operation"></a><span data-ttu-id="cb3e8-102">MResetZ işlemi</span><span class="sxs-lookup"><span data-stu-id="cb3e8-102">MResetZ operation</span></span>

<span data-ttu-id="cb3e8-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="cb3e8-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="cb3e8-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb3e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb3e8-105">Z tabanında tek bir qubit ölçer ve ölçüyü izleyen sabit bir başlangıç durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="cb3e8-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="cb3e8-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="cb3e8-106">Description</span></span>

<span data-ttu-id="cb3e8-107">$Z $-temelinde tek qubit ölçümü gerçekleştirir ve ölçü sonrasında qubitin $ \ket $ ' e döndürülmesini sağlar {0} .</span><span class="sxs-lookup"><span data-stu-id="cb3e8-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="cb3e8-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="cb3e8-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="cb3e8-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cb3e8-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cb3e8-110">Ölçülecek tek bir qubit.</span><span class="sxs-lookup"><span data-stu-id="cb3e8-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="cb3e8-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="cb3e8-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="cb3e8-112">`target`Pauli $Z $ tabanında ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="cb3e8-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>