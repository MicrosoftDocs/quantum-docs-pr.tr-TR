---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: Applykoşulsuz işlem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 67a4dcba5c193222c06ab429813adf12d7bbedfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847891"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="80874-102">Applykoşulsuz işlem</span><span class="sxs-lookup"><span data-stu-id="80874-102">ApplyConditionally operation</span></span>

<span data-ttu-id="80874-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="80874-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="80874-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="80874-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="80874-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="80874-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="80874-106">measurementResults: __geçersiz <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="80874-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="80874-107">resultsValues değerleri __: <Result> geçersiz__[]</span><span class="sxs-lookup"><span data-stu-id="80874-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="80874-108">onEqualOp: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80874-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="80874-109">equalArg: 'T</span><span class="sxs-lookup"><span data-stu-id="80874-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="80874-110">onNonEqualOp: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80874-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="80874-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="80874-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="80874-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80874-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="80874-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="80874-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="80874-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="80874-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="80874-115">' U</span><span class="sxs-lookup"><span data-stu-id="80874-115">'U</span></span>

