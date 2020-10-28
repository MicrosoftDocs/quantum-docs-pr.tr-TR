---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 81dd998353f674d55afe85dd20904047391bdb40
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731263"
---
# <a name="notequalcp-function"></a><span data-ttu-id="e4af5-102">NotEqualCP işlevi</span><span class="sxs-lookup"><span data-stu-id="e4af5-102">NotEqualCP function</span></span>

<span data-ttu-id="e4af5-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e4af5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e4af5-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4af5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4af5-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="e4af5-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="e4af5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e4af5-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="e4af5-107">y: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="e4af5-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="e4af5-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="e4af5-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="e4af5-109">b: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="e4af5-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="e4af5-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="e4af5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e4af5-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e4af5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e4af5-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="e4af5-112">`true` if and only if `a` is not equal to `b`.</span></span>