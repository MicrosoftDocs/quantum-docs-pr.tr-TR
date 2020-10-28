---
uid: Microsoft.Quantum.Logical.LessThanL
title: Lessbir l işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: fde57bcd9960056461bddac54300c298def8f7d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726036"
---
# <a name="lessthanl-function"></a><span data-ttu-id="fceb0-102">Lessbir l işlevi</span><span class="sxs-lookup"><span data-stu-id="fceb0-102">LessThanL function</span></span>

<span data-ttu-id="fceb0-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fceb0-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fceb0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fceb0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fceb0-105">Yalnızca bir sayı başka bir sayıdan küçükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="fceb0-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="fceb0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="fceb0-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="fceb0-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fceb0-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fceb0-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="fceb0-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="fceb0-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fceb0-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fceb0-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="fceb0-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fceb0-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fceb0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fceb0-112">`true` yalnızca ve ' `a` den tamamen küçükse `b` .</span><span class="sxs-lookup"><span data-stu-id="fceb0-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fceb0-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="fceb0-113">Remarks</span></span>

<span data-ttu-id="fceb0-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="fceb0-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```