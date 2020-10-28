---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: ApplyIfElseR işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: ca9db334bb62e043933f99e405612957831efdcb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733658"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="89a78-102">ApplyIfElseR işlemi</span><span class="sxs-lookup"><span data-stu-id="89a78-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="89a78-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="89a78-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="89a78-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="89a78-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="89a78-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="89a78-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="89a78-106">measurementResult: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="89a78-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="89a78-107">Onresultsıfırlaması op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89a78-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="89a78-108">Sıfırlama bağımsız değişkeni: 'T</span><span class="sxs-lookup"><span data-stu-id="89a78-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit"></a><span data-ttu-id="89a78-109">onResultOneOp: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89a78-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--u"></a><span data-ttu-id="89a78-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="89a78-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="89a78-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89a78-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="89a78-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="89a78-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="89a78-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="89a78-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="89a78-114">' U</span><span class="sxs-lookup"><span data-stu-id="89a78-114">'U</span></span>

