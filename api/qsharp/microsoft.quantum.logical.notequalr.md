---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725969"
---
# <a name="notequalr-function"></a><span data-ttu-id="eba28-102">NotEqualR işlevi</span><span class="sxs-lookup"><span data-stu-id="eba28-102">NotEqualR function</span></span>

<span data-ttu-id="eba28-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="eba28-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="eba28-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eba28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eba28-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="eba28-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="eba28-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="eba28-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="eba28-107">y: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="eba28-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="eba28-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="eba28-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="eba28-109">b: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="eba28-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="eba28-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="eba28-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="eba28-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="eba28-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="eba28-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="eba28-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="eba28-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="eba28-113">Remarks</span></span>

<span data-ttu-id="eba28-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="eba28-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```