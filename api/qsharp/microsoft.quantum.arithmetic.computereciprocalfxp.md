---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: e8f31d82fc69a3d7f4b571c4a679255dffc28b7f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731602"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="29845-102">ComputeReciprocalFxP işlemi</span><span class="sxs-lookup"><span data-stu-id="29845-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="29845-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="29845-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="29845-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29845-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="29845-105">$1/x $ ' i $x $ bir sabit noktalı sayı için hesaplar.</span><span class="sxs-lookup"><span data-stu-id="29845-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="29845-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="29845-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="29845-107">x: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="29845-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="29845-108">Ters çevrilme yapılacak sabit nokta sayısı.</span><span class="sxs-lookup"><span data-stu-id="29845-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="29845-109">Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="29845-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="29845-110">Sonucu alacak sabit noktalı sayı.</span><span class="sxs-lookup"><span data-stu-id="29845-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="29845-111">$ \Ket{0.0} $ olarak başlatılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="29845-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="29845-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="29845-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

