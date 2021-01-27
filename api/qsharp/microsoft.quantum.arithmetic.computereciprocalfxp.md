---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843253"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="d7bb2-102">ComputeReciprocalFxP işlemi</span><span class="sxs-lookup"><span data-stu-id="d7bb2-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="d7bb2-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d7bb2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d7bb2-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="d7bb2-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="d7bb2-105">$1/x $ ' i $x $ bir sabit noktalı sayı için hesaplar.</span><span class="sxs-lookup"><span data-stu-id="d7bb2-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d7bb2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d7bb2-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="d7bb2-107">x: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d7bb2-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d7bb2-108">Ters çevrilme yapılacak sabit nokta sayısı.</span><span class="sxs-lookup"><span data-stu-id="d7bb2-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="d7bb2-109">Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d7bb2-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d7bb2-110">Sonucu alacak sabit noktalı sayı.</span><span class="sxs-lookup"><span data-stu-id="d7bb2-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="d7bb2-111">$ \Ket{0.0} $ olarak başlatılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d7bb2-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7bb2-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7bb2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

