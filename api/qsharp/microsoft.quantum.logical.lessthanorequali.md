---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: Lesskıdan Okarşılandığından ali işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: dd934fde3fae9c1a43032b4b08ac03afa72798d1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726029"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="f2097-102">Lesskıdan Okarşılandığından ali işlevi</span><span class="sxs-lookup"><span data-stu-id="f2097-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="f2097-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f2097-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f2097-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f2097-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f2097-105">Yalnızca bir sayı başka bir sayıdan küçük veya ona eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="f2097-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="f2097-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f2097-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="f2097-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2097-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2097-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="f2097-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="f2097-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2097-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2097-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="f2097-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f2097-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f2097-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f2097-112">`true` ve yalnızca, değerinden `a` küçükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="f2097-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f2097-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f2097-113">Remarks</span></span>

<span data-ttu-id="f2097-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="f2097-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```