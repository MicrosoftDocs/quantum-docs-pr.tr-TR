---
uid: Microsoft.Quantum.Arithmetic.PrepareFxP
title: Hazırlık Efxp işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PrepareFxP
qsharp.summary: Initialize a quantum fixed-point number to a classical constant.
ms.openlocfilehash: 31ed1a170a47c77c21aa8b5c291860e422af2e3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845808"
---
# <a name="preparefxp-operation"></a><span data-ttu-id="5faa4-102">Hazırlık Efxp işlemi</span><span class="sxs-lookup"><span data-stu-id="5faa4-102">PrepareFxP operation</span></span>

<span data-ttu-id="5faa4-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5faa4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5faa4-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="5faa4-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="5faa4-105">Bir hisse ansız sabit noktalı sayıyı klasik bir sabit olarak başlatın.</span><span class="sxs-lookup"><span data-stu-id="5faa4-105">Initialize a quantum fixed-point number to a classical constant.</span></span>

```qsharp
operation PrepareFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5faa4-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5faa4-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="5faa4-107">Sabit: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5faa4-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5faa4-108">Hisse sabit noktalı sayının başlatıldığı sabit.</span><span class="sxs-lookup"><span data-stu-id="5faa4-108">Constant to which to initialize the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="5faa4-109">FP: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="5faa4-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="5faa4-110">Başlatılacak sabit noktalı sayı (FixedPoint türünde).</span><span class="sxs-lookup"><span data-stu-id="5faa4-110">Fixed-point number (of type FixedPoint) to initialize.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5faa4-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5faa4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

