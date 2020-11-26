---
uid: Microsoft.Quantum.Arithmetic.PrepareFxP
title: Hazırlık Efxp işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PrepareFxP
qsharp.summary: Initialize a quantum fixed-point number to a classical constant.
ms.openlocfilehash: 29ba66700db83d0786a70841c7b03843a9ae6219
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222414"
---
# <a name="preparefxp-operation"></a><span data-ttu-id="e6759-102">Hazırlık Efxp işlemi</span><span class="sxs-lookup"><span data-stu-id="e6759-102">PrepareFxP operation</span></span>

<span data-ttu-id="e6759-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e6759-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e6759-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="e6759-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="e6759-105">Bir hisse ansız sabit noktalı sayıyı klasik bir sabit olarak başlatın.</span><span class="sxs-lookup"><span data-stu-id="e6759-105">Initialize a quantum fixed-point number to a classical constant.</span></span>

```qsharp
operation PrepareFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e6759-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e6759-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="e6759-107">Sabit: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e6759-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e6759-108">Hisse sabit noktalı sayının başlatıldığı sabit.</span><span class="sxs-lookup"><span data-stu-id="e6759-108">Constant to which to initialize the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="e6759-109">FP: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="e6759-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="e6759-110">Başlatılacak sabit noktalı sayı (FixedPoint türünde).</span><span class="sxs-lookup"><span data-stu-id="e6759-110">Fixed-point number (of type FixedPoint) to initialize.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6759-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6759-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

