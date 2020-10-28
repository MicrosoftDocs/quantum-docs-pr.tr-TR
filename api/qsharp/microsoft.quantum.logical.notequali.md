---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 68e0e105a6b3742ec11e80ff92c39578a786aa85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725982"
---
# <a name="notequali-function"></a><span data-ttu-id="dd9d3-102">NotEqualI işlevi</span><span class="sxs-lookup"><span data-stu-id="dd9d3-102">NotEqualI function</span></span>

<span data-ttu-id="dd9d3-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="dd9d3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="dd9d3-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dd9d3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dd9d3-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="dd9d3-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="dd9d3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="dd9d3-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="dd9d3-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd9d3-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd9d3-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="dd9d3-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="dd9d3-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd9d3-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd9d3-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="dd9d3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="dd9d3-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dd9d3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dd9d3-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="dd9d3-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd9d3-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="dd9d3-113">Remarks</span></span>

<span data-ttu-id="dd9d3-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="dd9d3-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```