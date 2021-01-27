---
uid: Microsoft.Quantum.Arithmetic.SquareFxP
title: SquareFxP işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareFxP
qsharp.summary: Squares a fixed-point number.
ms.openlocfilehash: ba0364d7c649c2a949fc52f89409a5280f71a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842910"
---
# <a name="squarefxp-operation"></a><span data-ttu-id="7d0c7-102">SquareFxP işlemi</span><span class="sxs-lookup"><span data-stu-id="7d0c7-102">SquareFxP operation</span></span>

<span data-ttu-id="7d0c7-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7d0c7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7d0c7-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="7d0c7-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="7d0c7-105">Sabit noktalı bir sayı için kareler.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-105">Squares a fixed-point number.</span></span>

```qsharp
operation SquareFxP (fp : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7d0c7-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7d0c7-106">Input</span></span>

### <a name="fp--fixedpoint"></a><span data-ttu-id="7d0c7-107">FP: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="7d0c7-107">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="7d0c7-108">Sabit noktalı sayı.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-108">Fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="7d0c7-109">Sonuç: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="7d0c7-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="7d0c7-110">Sonuç sabit noktalı sayı, başlangıçta $ \ demet $ durumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="7d0c7-110">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d0c7-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d0c7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

