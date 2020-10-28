---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZero
title: ApplyIfZero işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZero
qsharp.summary: ''
ms.openlocfilehash: a76c6269ac4445326ac357fe2cdd552847089a6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732466"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="6a9da-102">ApplyIfZero işlemi</span><span class="sxs-lookup"><span data-stu-id="6a9da-102">ApplyIfZero operation</span></span>

<span data-ttu-id="6a9da-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="6a9da-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="6a9da-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6a9da-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZero<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="6a9da-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="6a9da-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="6a9da-106">measurementResult: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="6a9da-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="6a9da-107">Onresultsıfırlaması op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a9da-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="6a9da-108">Sıfırlama bağımsız değişkeni: 'T</span><span class="sxs-lookup"><span data-stu-id="6a9da-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="6a9da-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a9da-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6a9da-110">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="6a9da-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6a9da-111">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="6a9da-111">'T</span></span>

