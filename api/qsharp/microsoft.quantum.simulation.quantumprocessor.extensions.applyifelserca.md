---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRCA
title: ApplyIfElseRCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRCA
qsharp.summary: ''
ms.openlocfilehash: fb2f7ded44708a93d97d7041bf15be2c8c48990a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730698"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="a8aa7-102">ApplyIfElseRCA işlemi</span><span class="sxs-lookup"><span data-stu-id="a8aa7-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="a8aa7-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="a8aa7-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="a8aa7-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8aa7-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseRCA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj + Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj + Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="a8aa7-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="a8aa7-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="a8aa7-106">measurementResult: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="a8aa7-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-adj--ctl"></a><span data-ttu-id="a8aa7-107">Onresultsıfırlaması op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="a8aa7-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="a8aa7-108">Sıfırlama bağımsız değişkeni: 'T</span><span class="sxs-lookup"><span data-stu-id="a8aa7-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit-adj--ctl"></a><span data-ttu-id="a8aa7-109">onResultOneOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="a8aa7-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="a8aa7-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="a8aa7-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="a8aa7-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8aa7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a8aa7-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="a8aa7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a8aa7-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="a8aa7-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="a8aa7-114">' U</span><span class="sxs-lookup"><span data-stu-id="a8aa7-114">'U</span></span>

