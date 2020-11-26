---
uid: Microsoft.Quantum.Logical.Or
title: OR işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 7093d908696a8cfda6b5ef648f9dfafcfac97144
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197135"
---
# <a name="or-function"></a><span data-ttu-id="292d3-102">OR işlevi</span><span class="sxs-lookup"><span data-stu-id="292d3-102">Or function</span></span>

<span data-ttu-id="292d3-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="292d3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="292d3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="292d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="292d3-105">İki değerden oluşan Boole birleşim durumunu döndürür.</span><span class="sxs-lookup"><span data-stu-id="292d3-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="292d3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="292d3-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="292d3-107">y: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="292d3-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="292d3-108">Göz önünde bulundurmanız için ilk değer.</span><span class="sxs-lookup"><span data-stu-id="292d3-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="292d3-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="292d3-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="292d3-110">Göz önünde bulundurmanız için ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="292d3-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="292d3-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="292d3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="292d3-112">`true` yalnızca ya da varsa `a` `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="292d3-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="292d3-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="292d3-113">Remarks</span></span>

<span data-ttu-id="292d3-114">İşlecin aksine `or` , bu işlev kısa devre değildir, her iki giriş de tam olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="292d3-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="292d3-115">En fazla kısa devre davranýþý, şunlar eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="292d3-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```