---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: ApplyIfElseRC işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 21069c43c16bc9712973ac4e0afea8320c0d83a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725826"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="c4e7a-102">ApplyIfElseRC işlemi</span><span class="sxs-lookup"><span data-stu-id="c4e7a-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="c4e7a-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="c4e7a-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="c4e7a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4e7a-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="c4e7a-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="c4e7a-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="c4e7a-106">measurementResult: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="c4e7a-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-ctl"></a><span data-ttu-id="c4e7a-107">Onresultsıfırlaması op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="c4e7a-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="c4e7a-108">Sıfırlama bağımsız değişkeni: 'T</span><span class="sxs-lookup"><span data-stu-id="c4e7a-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit-ctl"></a><span data-ttu-id="c4e7a-109">onResultOneOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="c4e7a-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="c4e7a-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="c4e7a-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="c4e7a-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4e7a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c4e7a-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c4e7a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4e7a-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c4e7a-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="c4e7a-114">' U</span><span class="sxs-lookup"><span data-stu-id="c4e7a-114">'U</span></span>

