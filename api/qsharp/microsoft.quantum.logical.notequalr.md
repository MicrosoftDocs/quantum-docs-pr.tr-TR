---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4ac6cf4b220fa42c8eb946d6fbcad4cdb191afcd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197203"
---
# <a name="notequalr-function"></a><span data-ttu-id="20cab-102">NotEqualR işlevi</span><span class="sxs-lookup"><span data-stu-id="20cab-102">NotEqualR function</span></span>

<span data-ttu-id="20cab-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="20cab-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="20cab-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="20cab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="20cab-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="20cab-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="20cab-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="20cab-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="20cab-107">y: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="20cab-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="20cab-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="20cab-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="20cab-109">b: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="20cab-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="20cab-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="20cab-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="20cab-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="20cab-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="20cab-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="20cab-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="20cab-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="20cab-113">Remarks</span></span>

<span data-ttu-id="20cab-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="20cab-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```