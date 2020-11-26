---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneA
title: ApplyIfOneA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneA
qsharp.summary: ''
ms.openlocfilehash: 93a72ee7174b0022b1fe30cd779dfc57e96d8033
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228279"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="83d2c-102">ApplyIfOneA işlemi</span><span class="sxs-lookup"><span data-stu-id="83d2c-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="83d2c-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="83d2c-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="83d2c-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="83d2c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Adj), oneArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="83d2c-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="83d2c-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="83d2c-106">measurementResult: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="83d2c-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj"></a><span data-ttu-id="83d2c-107">onResultOneOp: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="83d2c-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="83d2c-108">oneArg: 'T</span><span class="sxs-lookup"><span data-stu-id="83d2c-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="83d2c-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="83d2c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="83d2c-110">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="83d2c-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="83d2c-111">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="83d2c-111">'T</span></span>

