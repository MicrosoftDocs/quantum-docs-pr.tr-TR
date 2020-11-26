---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: Lesskıdan Okarşılandığından ali işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: b2974c9bc84d0b4366767f47682ab542f85063e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197575"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="2a9da-102">Lesskıdan Okarşılandığından ali işlevi</span><span class="sxs-lookup"><span data-stu-id="2a9da-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="2a9da-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2a9da-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2a9da-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2a9da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2a9da-105">Yalnızca bir sayı başka bir sayıdan küçük veya ona eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="2a9da-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="2a9da-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2a9da-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="2a9da-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a9da-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a9da-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="2a9da-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="2a9da-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a9da-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a9da-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="2a9da-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2a9da-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2a9da-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2a9da-112">`true` ve yalnızca, değerinden `a` küçükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="2a9da-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a9da-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2a9da-113">Remarks</span></span>

<span data-ttu-id="2a9da-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="2a9da-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```