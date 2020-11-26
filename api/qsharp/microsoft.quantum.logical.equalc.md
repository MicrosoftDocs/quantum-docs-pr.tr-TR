---
uid: Microsoft.Quantum.Logical.EqualC
title: EqualC işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualC
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 4c511489888613d95adaf154c005b3211af75446
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198393"
---
# <a name="equalc-function"></a><span data-ttu-id="468cb-102">EqualC işlevi</span><span class="sxs-lookup"><span data-stu-id="468cb-102">EqualC function</span></span>

<span data-ttu-id="468cb-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="468cb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="468cb-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="468cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="468cb-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="468cb-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="468cb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="468cb-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="468cb-107">y: [karmaşık](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="468cb-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="468cb-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="468cb-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="468cb-109">b: [karmaşık](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="468cb-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="468cb-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="468cb-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="468cb-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="468cb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="468cb-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="468cb-112">`true` if and only if `a` is equal to `b`.</span></span>