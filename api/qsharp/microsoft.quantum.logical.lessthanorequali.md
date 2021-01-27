---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: Lesskıdan Okarşılandığından ali işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 9438fc05b4ccb041b087f9cfeb30ac0c8cfcabd6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815618"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="a706c-102">Lesskıdan Okarşılandığından ali işlevi</span><span class="sxs-lookup"><span data-stu-id="a706c-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="a706c-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a706c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a706c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a706c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a706c-105">Yalnızca bir sayı başka bir sayıdan küçük veya ona eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="a706c-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="a706c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a706c-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a706c-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a706c-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a706c-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="a706c-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="a706c-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a706c-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a706c-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="a706c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a706c-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a706c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a706c-112">`true` ve yalnızca, değerinden `a` küçükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="a706c-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a706c-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a706c-113">Remarks</span></span>

<span data-ttu-id="a706c-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="a706c-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```