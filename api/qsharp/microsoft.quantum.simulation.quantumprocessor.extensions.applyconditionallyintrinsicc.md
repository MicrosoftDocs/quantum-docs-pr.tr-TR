---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicC
title: ApplyConditionallyIntrinsicC işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 54367d89636eb69462040e83cc3c4b6a9f734c0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730863"
---
# <a name="applyconditionallyintrinsicc-operation"></a><span data-ttu-id="37501-102">ApplyConditionallyIntrinsicC işlemi</span><span class="sxs-lookup"><span data-stu-id="37501-102">ApplyConditionallyIntrinsicC operation</span></span>

<span data-ttu-id="37501-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="37501-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="37501-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37501-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicC (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl), onNonEqualOp : (Unit => Unit is Ctl)) : Unit
```


## <a name="input"></a><span data-ttu-id="37501-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="37501-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="37501-106">measurementResults: __geçersiz <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="37501-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="37501-107">resultsValues değerleri __: <Result> geçersiz__ []</span><span class="sxs-lookup"><span data-stu-id="37501-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--unit--unit-ctl"></a><span data-ttu-id="37501-108">onequalop: [birim](xref:microsoft.quantum.lang-ref.unit) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="37501-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onnonequalop--unit--unit-ctl"></a><span data-ttu-id="37501-109">onnonequalop: [birim](xref:microsoft.quantum.lang-ref.unit) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="37501-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="37501-110">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37501-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

