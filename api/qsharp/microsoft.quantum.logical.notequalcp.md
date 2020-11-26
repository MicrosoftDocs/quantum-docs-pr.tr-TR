---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: df735408f76eb6b88f0d867021d69b83edd69b7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197305"
---
# <a name="notequalcp-function"></a><span data-ttu-id="7d943-102">NotEqualCP işlevi</span><span class="sxs-lookup"><span data-stu-id="7d943-102">NotEqualCP function</span></span>

<span data-ttu-id="7d943-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7d943-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7d943-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d943-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d943-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="7d943-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="7d943-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7d943-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="7d943-107">y: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="7d943-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="7d943-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="7d943-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="7d943-109">b: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="7d943-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="7d943-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="7d943-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7d943-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7d943-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7d943-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="7d943-112">`true` if and only if `a` is not equal to `b`.</span></span>