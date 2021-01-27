---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: ApplyIfElseR işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: d4306e594c49c0863c1284fc4775b5f3c7d73bda
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855680"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="eafe8-102">ApplyIfElseR işlemi</span><span class="sxs-lookup"><span data-stu-id="eafe8-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="eafe8-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="eafe8-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="eafe8-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="eafe8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="eafe8-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="eafe8-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="eafe8-106">measurementResult: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="eafe8-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="eafe8-107">Onresultsıfırlaması op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eafe8-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="eafe8-108">Sıfırlama bağımsız değişkeni: 'T</span><span class="sxs-lookup"><span data-stu-id="eafe8-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit"></a><span data-ttu-id="eafe8-109">onResultOneOp: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eafe8-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--u"></a><span data-ttu-id="eafe8-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="eafe8-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="eafe8-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eafe8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eafe8-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="eafe8-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eafe8-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="eafe8-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="eafe8-114">' U</span><span class="sxs-lookup"><span data-stu-id="eafe8-114">'U</span></span>

