---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: ApplyIfElseR işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: 9e391b61aa4d22ad02bf657a866f959d35b6628f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192681"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="f454a-102">ApplyIfElseR işlemi</span><span class="sxs-lookup"><span data-stu-id="f454a-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="f454a-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="f454a-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="f454a-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f454a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="f454a-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="f454a-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="f454a-106">measurementResult: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="f454a-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="f454a-107">Onresultsıfırlaması op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f454a-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="f454a-108">Sıfırlama bağımsız değişkeni: 'T</span><span class="sxs-lookup"><span data-stu-id="f454a-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit"></a><span data-ttu-id="f454a-109">onResultOneOp: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f454a-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--u"></a><span data-ttu-id="f454a-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="f454a-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="f454a-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f454a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f454a-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f454a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f454a-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f454a-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="f454a-114">' U</span><span class="sxs-lookup"><span data-stu-id="f454a-114">'U</span></span>

