---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRA
title: ApplyIfElseRA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRA
qsharp.summary: ''
ms.openlocfilehash: bcc52c6e2b4dfc6354e12c57e19739ac021d2e8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734026"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="b2f86-102">ApplyIfElseRA işlemi</span><span class="sxs-lookup"><span data-stu-id="b2f86-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="b2f86-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="b2f86-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="b2f86-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2f86-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseRA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="b2f86-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="b2f86-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="b2f86-106">measurementResult: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="b2f86-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-adj"></a><span data-ttu-id="b2f86-107">Onresultsıfırlaması op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="b2f86-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="b2f86-108">Sıfırlama bağımsız değişkeni: 'T</span><span class="sxs-lookup"><span data-stu-id="b2f86-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit-adj"></a><span data-ttu-id="b2f86-109">onResultOneOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="b2f86-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="onearg--u"></a><span data-ttu-id="b2f86-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="b2f86-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="b2f86-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2f86-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b2f86-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="b2f86-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b2f86-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="b2f86-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="b2f86-114">' U</span><span class="sxs-lookup"><span data-stu-id="b2f86-114">'U</span></span>

