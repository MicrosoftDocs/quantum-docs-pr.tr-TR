---
uid: Microsoft.Quantum.Logical.And
title: And işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 279221ed785dd76e28146e4c22e70290936bf529
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198580"
---
# <a name="and-function"></a><span data-ttu-id="fb840-102">And işlevi</span><span class="sxs-lookup"><span data-stu-id="fb840-102">And function</span></span>

<span data-ttu-id="fb840-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fb840-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fb840-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb840-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb840-105">İki değerden oluşan Boole değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="fb840-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="fb840-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="fb840-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="fb840-107">y: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fb840-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fb840-108">Göz önünde bulundurmanız için ilk değer.</span><span class="sxs-lookup"><span data-stu-id="fb840-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="fb840-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fb840-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fb840-110">Göz önünde bulundurmanız için ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="fb840-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fb840-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fb840-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fb840-112">`true` ve yalnızca ise `a` ve ise `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="fb840-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fb840-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="fb840-113">Remarks</span></span>

<span data-ttu-id="fb840-114">İşlecin aksine `and` , bu işlev kısa devre değildir, her iki giriş de tam olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="fb840-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="fb840-115">En fazla kısa devre davranýþý, şunlar eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="fb840-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```