---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneCA
title: ApplyIfOneCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneCA
qsharp.summary: ''
ms.openlocfilehash: e997cf4b20fdd2c52285191b732297ca99886c22
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230948"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="7bc00-102">ApplyIfOneCA işlemi</span><span class="sxs-lookup"><span data-stu-id="7bc00-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="7bc00-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="7bc00-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="7bc00-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7bc00-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneCA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl + Adj), oneArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7bc00-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="7bc00-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="7bc00-106">measurementResult: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="7bc00-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj--ctl"></a><span data-ttu-id="7bc00-107">onResultOneOp: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="7bc00-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="7bc00-108">oneArg: 'T</span><span class="sxs-lookup"><span data-stu-id="7bc00-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="7bc00-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7bc00-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7bc00-110">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="7bc00-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7bc00-111">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="7bc00-111">'T</span></span>

