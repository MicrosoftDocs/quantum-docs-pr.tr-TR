---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: Lesskımı Okarşılandığından ALL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 1de3fdb0fa53fef9cbf4b9ee9b6a1c54865bd093
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849110"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="cb617-102">Lesskımı Okarşılandığından ALL işlevi</span><span class="sxs-lookup"><span data-stu-id="cb617-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="cb617-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cb617-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cb617-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb617-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb617-105">Yalnızca bir sayı başka bir sayıdan küçük veya ona eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="cb617-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="cb617-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="cb617-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="cb617-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cb617-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cb617-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="cb617-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="cb617-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cb617-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cb617-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="cb617-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cb617-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cb617-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cb617-112">`true` ve yalnızca, değerinden `a` küçükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="cb617-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb617-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cb617-113">Remarks</span></span>

<span data-ttu-id="cb617-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="cb617-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```