---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneCA
title: ApplyIfOneCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneCA
qsharp.summary: ''
ms.openlocfilehash: d8f388698c0c6d1557c7903ec68b317728986031
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734186"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="fce7d-102">ApplyIfOneCA işlemi</span><span class="sxs-lookup"><span data-stu-id="fce7d-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="fce7d-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="fce7d-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="fce7d-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fce7d-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOneCA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl + Adj), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="fce7d-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="fce7d-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="fce7d-106">measurementResult: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="fce7d-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit-ctl--adj"></a><span data-ttu-id="fce7d-107">onResultOneOp: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL + ayarlanabilir</span><span class="sxs-lookup"><span data-stu-id="fce7d-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="fce7d-108">oneArg: 'T</span><span class="sxs-lookup"><span data-stu-id="fce7d-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="fce7d-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fce7d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fce7d-110">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="fce7d-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fce7d-111">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="fce7d-111">'T</span></span>

