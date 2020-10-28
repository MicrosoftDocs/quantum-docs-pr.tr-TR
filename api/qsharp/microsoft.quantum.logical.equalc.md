---
uid: Microsoft.Quantum.Logical.EqualC
title: EqualC işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualC
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 8b0c34915ef392e8a84706f601da71f3848a3134
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731282"
---
# <a name="equalc-function"></a><span data-ttu-id="ca506-102">EqualC işlevi</span><span class="sxs-lookup"><span data-stu-id="ca506-102">EqualC function</span></span>

<span data-ttu-id="ca506-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ca506-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ca506-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ca506-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ca506-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="ca506-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="ca506-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ca506-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="ca506-107">y: [karmaşık](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="ca506-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="ca506-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="ca506-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="ca506-109">b: [karmaşık](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="ca506-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="ca506-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="ca506-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ca506-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ca506-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ca506-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="ca506-112">`true` if and only if `a` is equal to `b`.</span></span>