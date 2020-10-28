---
uid: Microsoft.Quantum.Logical.LessThanI
title: Lessdim i işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 204e62a87d2b3d0070946985030d038ead686457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732922"
---
# <a name="lessthani-function"></a><span data-ttu-id="3f042-102">Lessdim i işlevi</span><span class="sxs-lookup"><span data-stu-id="3f042-102">LessThanI function</span></span>

<span data-ttu-id="3f042-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3f042-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3f042-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f042-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f042-105">Yalnızca bir sayı başka bir sayıdan küçükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="3f042-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="3f042-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3f042-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="3f042-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3f042-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3f042-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="3f042-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="3f042-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3f042-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3f042-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="3f042-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3f042-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3f042-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3f042-112">`true` yalnızca ve ' `a` den tamamen küçükse `b` .</span><span class="sxs-lookup"><span data-stu-id="3f042-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f042-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3f042-113">Remarks</span></span>

<span data-ttu-id="3f042-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="3f042-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```