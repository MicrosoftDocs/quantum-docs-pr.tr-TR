---
uid: Microsoft.Quantum.Logical.Or
title: OR işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730754"
---
# <a name="or-function"></a><span data-ttu-id="78c0a-102">OR işlevi</span><span class="sxs-lookup"><span data-stu-id="78c0a-102">Or function</span></span>

<span data-ttu-id="78c0a-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="78c0a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="78c0a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="78c0a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="78c0a-105">İki değerden oluşan Boole birleşim durumunu döndürür.</span><span class="sxs-lookup"><span data-stu-id="78c0a-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="78c0a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="78c0a-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="78c0a-107">y: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="78c0a-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="78c0a-108">Göz önünde bulundurmanız için ilk değer.</span><span class="sxs-lookup"><span data-stu-id="78c0a-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="78c0a-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="78c0a-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="78c0a-110">Göz önünde bulundurmanız için ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="78c0a-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="78c0a-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="78c0a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="78c0a-112">`true` yalnızca ya da varsa `a` `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="78c0a-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="78c0a-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="78c0a-113">Remarks</span></span>

<span data-ttu-id="78c0a-114">İşlecin aksine `or` , bu işlev kısa devre değildir, her iki giriş de tam olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="78c0a-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="78c0a-115">En fazla kısa devre davranýþý, şunlar eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="78c0a-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```