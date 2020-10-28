---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733794"
---
# <a name="mresety-operation"></a><span data-ttu-id="2c27e-102">MResetY işlemi</span><span class="sxs-lookup"><span data-stu-id="2c27e-102">MResetY operation</span></span>

<span data-ttu-id="2c27e-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="2c27e-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="2c27e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c27e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c27e-105">Y temelinde tek bir qubit ölçer ve ölçüyü izleyen sabit bir başlangıç durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="2c27e-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="2c27e-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2c27e-106">Description</span></span>

<span data-ttu-id="2c27e-107">$Y $-temelinde tek qubit ölçümü gerçekleştirir ve ölçü sonrasında qubitin $ \ket $ ' e döndürülmesini sağlar {0} .</span><span class="sxs-lookup"><span data-stu-id="2c27e-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="2c27e-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="2c27e-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="2c27e-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2c27e-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2c27e-110">Ölçülecek tek bir qubit.</span><span class="sxs-lookup"><span data-stu-id="2c27e-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="2c27e-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="2c27e-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="2c27e-112">`target`Pauli $Y $ tabanında ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="2c27e-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>