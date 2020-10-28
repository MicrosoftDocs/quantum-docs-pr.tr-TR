---
uid: Microsoft.Quantum.Logical.And
title: And işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731303"
---
# <a name="and-function"></a><span data-ttu-id="3e949-102">And işlevi</span><span class="sxs-lookup"><span data-stu-id="3e949-102">And function</span></span>

<span data-ttu-id="3e949-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3e949-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3e949-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e949-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e949-105">İki değerden oluşan Boole değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="3e949-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="3e949-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3e949-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="3e949-107">y: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3e949-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3e949-108">Göz önünde bulundurmanız için ilk değer.</span><span class="sxs-lookup"><span data-stu-id="3e949-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="3e949-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3e949-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3e949-110">Göz önünde bulundurmanız için ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="3e949-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3e949-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3e949-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3e949-112">`true` ve yalnızca ise `a` ve ise `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="3e949-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e949-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3e949-113">Remarks</span></span>

<span data-ttu-id="3e949-114">İşlecin aksine `and` , bu işlev kısa devre değildir, her iki giriş de tam olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="3e949-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="3e949-115">En fazla kısa devre davranýþý, şunlar eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="3e949-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```