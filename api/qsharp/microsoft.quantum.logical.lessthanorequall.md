---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: Lesskımı Okarşılandığından ALL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 2322ae4dd6025108d322d29770f42953213aa025
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197610"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="69a18-102">Lesskımı Okarşılandığından ALL işlevi</span><span class="sxs-lookup"><span data-stu-id="69a18-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="69a18-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="69a18-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="69a18-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69a18-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69a18-105">Yalnızca bir sayı başka bir sayıdan küçük veya ona eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="69a18-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="69a18-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="69a18-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="69a18-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="69a18-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="69a18-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="69a18-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="69a18-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="69a18-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="69a18-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="69a18-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="69a18-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="69a18-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="69a18-112">`true` ve yalnızca, değerinden `a` küçükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="69a18-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="69a18-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="69a18-113">Remarks</span></span>

<span data-ttu-id="69a18-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="69a18-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```