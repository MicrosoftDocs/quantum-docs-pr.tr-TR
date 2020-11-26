---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 36c6f227135b5ccaf1146fd7afdc8205d416c5dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227038"
---
# <a name="mresety-operation"></a><span data-ttu-id="6b5c7-102">MResetY işlemi</span><span class="sxs-lookup"><span data-stu-id="6b5c7-102">MResetY operation</span></span>

<span data-ttu-id="6b5c7-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="6b5c7-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="6b5c7-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6b5c7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6b5c7-105">Y temelinde tek bir qubit ölçer ve ölçüyü izleyen sabit bir başlangıç durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="6b5c7-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6b5c7-106">Description</span></span>

<span data-ttu-id="6b5c7-107">$Y $-temelinde tek qubit ölçümü gerçekleştirir ve ölçü sonrasında qubitin $ \ket $ ' e döndürülmesini sağlar {0} .</span><span class="sxs-lookup"><span data-stu-id="6b5c7-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="6b5c7-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="6b5c7-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="6b5c7-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6b5c7-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6b5c7-110">Ölçülecek tek bir qubit.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="6b5c7-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="6b5c7-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="6b5c7-112">`target`Pauli $Y $ tabanında ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="6b5c7-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>