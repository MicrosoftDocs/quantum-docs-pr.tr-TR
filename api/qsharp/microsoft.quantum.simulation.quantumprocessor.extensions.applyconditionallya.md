---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: ApplyConditionallyA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: b6f7e7d6d51e531b0ec9e7e4f2f5772038421933
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726282"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="7b11c-102">ApplyConditionallyA işlemi</span><span class="sxs-lookup"><span data-stu-id="7b11c-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="7b11c-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="7b11c-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="7b11c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7b11c-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="7b11c-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="7b11c-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="7b11c-106">measurementResults: __geçersiz <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="7b11c-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="7b11c-107">resultsValues değerleri __: <Result> geçersiz__ []</span><span class="sxs-lookup"><span data-stu-id="7b11c-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit-adj"></a><span data-ttu-id="7b11c-108">onEqualOp: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="7b11c-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="7b11c-109">equalArg: 'T</span><span class="sxs-lookup"><span data-stu-id="7b11c-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit-adj"></a><span data-ttu-id="7b11c-110">onNonEqualOp: ' U => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama</span><span class="sxs-lookup"><span data-stu-id="7b11c-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="7b11c-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="7b11c-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="7b11c-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b11c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7b11c-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="7b11c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7b11c-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="7b11c-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="7b11c-115">' U</span><span class="sxs-lookup"><span data-stu-id="7b11c-115">'U</span></span>

