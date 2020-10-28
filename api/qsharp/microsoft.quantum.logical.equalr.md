---
uid: Microsoft.Quantum.Logical.EqualR
title: EqualR işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726071"
---
# <a name="equalr-function"></a><span data-ttu-id="d4feb-102">EqualR işlevi</span><span class="sxs-lookup"><span data-stu-id="d4feb-102">EqualR function</span></span>

<span data-ttu-id="d4feb-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d4feb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d4feb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4feb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4feb-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="d4feb-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="d4feb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d4feb-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="d4feb-107">y: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="d4feb-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="d4feb-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="d4feb-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="d4feb-109">b: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="d4feb-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="d4feb-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="d4feb-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d4feb-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d4feb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d4feb-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="d4feb-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d4feb-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d4feb-113">Remarks</span></span>

<span data-ttu-id="d4feb-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="d4feb-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```