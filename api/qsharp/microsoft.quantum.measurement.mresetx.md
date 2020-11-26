---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 04fb0f84ddf79a3d2cfc21fdaabd16c129f6d72f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194211"
---
# <a name="mresetx-operation"></a><span data-ttu-id="9499f-102">MResetX işlemi</span><span class="sxs-lookup"><span data-stu-id="9499f-102">MResetX operation</span></span>

<span data-ttu-id="9499f-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="9499f-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="9499f-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9499f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9499f-105">X temelinde tek bir qubit ölçer ve ölçüyü izleyen sabit bir başlangıç durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="9499f-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="9499f-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9499f-106">Description</span></span>

<span data-ttu-id="9499f-107">$X $-temelinde tek qubit ölçümü gerçekleştirir ve ölçü sonrasında qubitin $ \ket $ ' e döndürülmesini sağlar {0} .</span><span class="sxs-lookup"><span data-stu-id="9499f-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="9499f-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="9499f-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="9499f-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9499f-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9499f-110">Ölçülecek tek bir qubit.</span><span class="sxs-lookup"><span data-stu-id="9499f-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="9499f-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="9499f-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="9499f-112">`target`Pauli $X $ tabanında ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="9499f-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>