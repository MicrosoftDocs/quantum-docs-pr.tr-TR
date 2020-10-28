---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: ApplyConditionallyCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: e456ed5d8f7f17a914401473948c89c020174903
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730887"
---
# <a name="applyconditionallyca-operation"></a><span data-ttu-id="023e6-102">ApplyConditionallyCA işlemi</span><span class="sxs-lookup"><span data-stu-id="023e6-102">ApplyConditionallyCA operation</span></span>

<span data-ttu-id="023e6-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="023e6-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="023e6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="023e6-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="023e6-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="023e6-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="023e6-106">measurementResults: __geçersiz <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="023e6-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="023e6-107">resultsValues değerleri __: <Result> geçersiz__ []</span><span class="sxs-lookup"><span data-stu-id="023e6-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit-ctl--adj"></a><span data-ttu-id="023e6-108">onEqualOp: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL + ayarlanabilir</span><span class="sxs-lookup"><span data-stu-id="023e6-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="023e6-109">equalArg: 'T</span><span class="sxs-lookup"><span data-stu-id="023e6-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit-ctl--adj"></a><span data-ttu-id="023e6-110">onNonEqualOp: ' U => [birim](xref:microsoft.quantum.lang-ref.unit) CTL + ayarlanabilir</span><span class="sxs-lookup"><span data-stu-id="023e6-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="023e6-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="023e6-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="023e6-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="023e6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="023e6-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="023e6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="023e6-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="023e6-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="023e6-115">' U</span><span class="sxs-lookup"><span data-stu-id="023e6-115">'U</span></span>

