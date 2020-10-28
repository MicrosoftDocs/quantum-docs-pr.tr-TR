---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicCA
title: ApplyConditionallyIntrinsicCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 7cdddba45824d5e5037270d8578f2cb16c03be83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730858"
---
# <a name="applyconditionallyintrinsicca-operation"></a><span data-ttu-id="4e451-102">ApplyConditionallyIntrinsicCA işlemi</span><span class="sxs-lookup"><span data-stu-id="4e451-102">ApplyConditionallyIntrinsicCA operation</span></span>

<span data-ttu-id="4e451-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="4e451-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="4e451-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e451-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicCA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl + Adj), onNonEqualOp : (Unit => Unit is Ctl + Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="4e451-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="4e451-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="4e451-106">measurementResults: __geçersiz <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="4e451-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="4e451-107">resultsValues değerleri __: <Result> geçersiz__ []</span><span class="sxs-lookup"><span data-stu-id="4e451-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--unit--unit-ctl--adj"></a><span data-ttu-id="4e451-108">onequalop: [birim](xref:microsoft.quantum.lang-ref.unit) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL + ayarlanabilir</span><span class="sxs-lookup"><span data-stu-id="4e451-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="onnonequalop--unit--unit-ctl--adj"></a><span data-ttu-id="4e451-109">onnonequalop: [birim](xref:microsoft.quantum.lang-ref.unit) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL + sıfatı</span><span class="sxs-lookup"><span data-stu-id="4e451-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="4e451-110">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e451-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

