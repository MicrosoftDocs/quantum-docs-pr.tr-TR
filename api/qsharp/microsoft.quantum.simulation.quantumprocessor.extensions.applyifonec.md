---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneC
title: ApplyIfOneC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneC
qsharp.summary: ''
ms.openlocfilehash: d7c4e39ba26befeabad612e888da4abd00efaeb5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230965"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="21ff5-102">ApplyIfOneC işlemi</span><span class="sxs-lookup"><span data-stu-id="21ff5-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="21ff5-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="21ff5-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="21ff5-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="21ff5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneC<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl), oneArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="21ff5-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="21ff5-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="21ff5-106">measurementResult: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="21ff5-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-ctl"></a><span data-ttu-id="21ff5-107">onResultOneOp: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="21ff5-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="21ff5-108">oneArg: 'T</span><span class="sxs-lookup"><span data-stu-id="21ff5-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="21ff5-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="21ff5-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="21ff5-110">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="21ff5-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="21ff5-111">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="21ff5-111">'T</span></span>

