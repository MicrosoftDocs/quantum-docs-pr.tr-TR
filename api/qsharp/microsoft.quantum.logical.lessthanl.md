---
uid: Microsoft.Quantum.Logical.LessThanL
title: Lessbir l işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 9a0678569596ac188c87c3944f3759783fcc77ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197730"
---
# <a name="lessthanl-function"></a><span data-ttu-id="d8221-102">Lessbir l işlevi</span><span class="sxs-lookup"><span data-stu-id="d8221-102">LessThanL function</span></span>

<span data-ttu-id="d8221-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d8221-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d8221-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8221-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d8221-105">Yalnızca bir sayı başka bir sayıdan küçükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="d8221-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="d8221-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d8221-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="d8221-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d8221-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d8221-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="d8221-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="d8221-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d8221-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d8221-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="d8221-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d8221-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d8221-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d8221-112">`true` yalnızca ve ' `a` den tamamen küçükse `b` .</span><span class="sxs-lookup"><span data-stu-id="d8221-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d8221-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d8221-113">Remarks</span></span>

<span data-ttu-id="d8221-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="d8221-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```