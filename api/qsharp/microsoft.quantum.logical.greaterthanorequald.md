---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 9d794fa94c1ccbde4030c90198fd7c7654469876
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726647"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="193ad-102">GreaterThanOrEqualD işlevi</span><span class="sxs-lookup"><span data-stu-id="193ad-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="193ad-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="193ad-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="193ad-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="193ad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="193ad-105">Yalnızca bir sayı başka bir sayıdan büyük veya buna eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="193ad-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="193ad-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="193ad-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="193ad-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="193ad-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="193ad-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="193ad-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="193ad-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="193ad-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="193ad-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="193ad-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="193ad-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="193ad-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="193ad-112">`true` ve yalnızca `a` değerinden büyükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="193ad-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="193ad-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="193ad-113">Remarks</span></span>

<span data-ttu-id="193ad-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="193ad-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```