---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: c8ee7e6a04cc2478f1c97fcc1d964a1574f7b1fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731274"
---
# <a name="equalcp-function"></a><span data-ttu-id="42f50-102">EqualCP işlevi</span><span class="sxs-lookup"><span data-stu-id="42f50-102">EqualCP function</span></span>

<span data-ttu-id="42f50-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="42f50-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="42f50-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="42f50-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="42f50-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="42f50-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="42f50-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="42f50-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="42f50-107">y: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="42f50-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="42f50-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="42f50-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="42f50-109">b: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="42f50-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="42f50-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="42f50-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="42f50-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="42f50-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="42f50-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="42f50-112">`true` if and only if `a` is equal to `b`.</span></span>