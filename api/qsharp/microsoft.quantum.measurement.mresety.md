---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 2e41e76a46b68178a8a22b39131d6ca2a8c50b64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854647"
---
# <a name="mresety-operation"></a><span data-ttu-id="b6083-102">MResetY işlemi</span><span class="sxs-lookup"><span data-stu-id="b6083-102">MResetY operation</span></span>

<span data-ttu-id="b6083-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="b6083-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="b6083-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b6083-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b6083-105">Y temelinde tek bir qubit ölçer ve ölçüyü izleyen sabit bir başlangıç durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="b6083-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="b6083-106">Description</span><span class="sxs-lookup"><span data-stu-id="b6083-106">Description</span></span>

<span data-ttu-id="b6083-107">$Y $-temelinde tek qubit ölçümü gerçekleştirir ve ölçü sonrasında qubitin $ \ket $ ' e döndürülmesini sağlar {0} .</span><span class="sxs-lookup"><span data-stu-id="b6083-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="b6083-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="b6083-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="b6083-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b6083-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b6083-110">Ölçülecek tek bir qubit.</span><span class="sxs-lookup"><span data-stu-id="b6083-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="b6083-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="b6083-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="b6083-112">`target`Pauli $Y $ tabanında ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="b6083-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>