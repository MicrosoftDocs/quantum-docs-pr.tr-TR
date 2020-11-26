---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: e3175b9b6fd2890963de0452102e2f0de1026b91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198240"
---
# <a name="equalcp-function"></a><span data-ttu-id="67f8c-102">EqualCP işlevi</span><span class="sxs-lookup"><span data-stu-id="67f8c-102">EqualCP function</span></span>

<span data-ttu-id="67f8c-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="67f8c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="67f8c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67f8c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67f8c-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="67f8c-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="67f8c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="67f8c-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="67f8c-107">y: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="67f8c-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="67f8c-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="67f8c-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="67f8c-109">b: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="67f8c-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="67f8c-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="67f8c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="67f8c-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="67f8c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="67f8c-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="67f8c-112">`true` if and only if `a` is equal to `b`.</span></span>