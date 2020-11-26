---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: Applyifsıfırlaması c işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: 9a73ea9ec607bec89c996c096b235a72185b453d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230846"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="43d5b-102">Applyifsıfırlaması c işlemi</span><span class="sxs-lookup"><span data-stu-id="43d5b-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="43d5b-103">Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="43d5b-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="43d5b-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="43d5b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="43d5b-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="43d5b-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="43d5b-106">measurementResult: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="43d5b-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="43d5b-107">Onresultsıfırlaması op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="43d5b-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="43d5b-108">Sıfırlama bağımsız değişkeni: 'T</span><span class="sxs-lookup"><span data-stu-id="43d5b-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="43d5b-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="43d5b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="43d5b-110">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="43d5b-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="43d5b-111">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="43d5b-111">'T</span></span>

