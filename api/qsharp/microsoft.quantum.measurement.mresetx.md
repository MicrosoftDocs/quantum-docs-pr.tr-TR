---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 44459e681daf1d28ce7d45f91ad59059babe5716
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853750"
---
# <a name="mresetx-operation"></a><span data-ttu-id="abcda-102">MResetX işlemi</span><span class="sxs-lookup"><span data-stu-id="abcda-102">MResetX operation</span></span>

<span data-ttu-id="abcda-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="abcda-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="abcda-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="abcda-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="abcda-105">X temelinde tek bir qubit ölçer ve ölçüyü izleyen sabit bir başlangıç durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="abcda-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="abcda-106">Description</span><span class="sxs-lookup"><span data-stu-id="abcda-106">Description</span></span>

<span data-ttu-id="abcda-107">$X $-temelinde tek qubit ölçümü gerçekleştirir ve ölçü sonrasında qubitin $ \ket $ ' e döndürülmesini sağlar {0} .</span><span class="sxs-lookup"><span data-stu-id="abcda-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="abcda-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="abcda-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="abcda-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="abcda-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="abcda-110">Ölçülecek tek bir qubit.</span><span class="sxs-lookup"><span data-stu-id="abcda-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="abcda-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="abcda-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="abcda-112">`target`Pauli $X $ tabanında ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="abcda-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>