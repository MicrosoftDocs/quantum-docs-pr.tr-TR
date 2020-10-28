---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsic
title: ApplyConditionallyIntrinsic işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsic
qsharp.summary: ''
ms.openlocfilehash: 892e3140544d0b02c5fef085c89c3a4c8bafcde5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730882"
---
# <a name="applyconditionallyintrinsic-operation"></a><span data-ttu-id="c03a1-102">ApplyConditionallyIntrinsic işlemi</span><span class="sxs-lookup"><span data-stu-id="c03a1-102">ApplyConditionallyIntrinsic operation</span></span>

<span data-ttu-id="c03a1-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="c03a1-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="c03a1-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c03a1-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyIntrinsic (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit), onNonEqualOp : (Unit => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="c03a1-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="c03a1-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="c03a1-106">measurementResults: __geçersiz <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="c03a1-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="c03a1-107">resultsValues değerleri __: <Result> geçersiz__ []</span><span class="sxs-lookup"><span data-stu-id="c03a1-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--unit--unit"></a><span data-ttu-id="c03a1-108">onequalop: [birim](xref:microsoft.quantum.lang-ref.unit) => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c03a1-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onnonequalop--unit--unit"></a><span data-ttu-id="c03a1-109">onnonequalop: [birim](xref:microsoft.quantum.lang-ref.unit) => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c03a1-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="c03a1-110">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c03a1-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

