---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: Lesskıt Okarşılandığından ald işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 3f4ccb0888e7df7c43ff73be8a3140e3fa84d4dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197645"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="1f5f9-102">Lesskıt Okarşılandığından ald işlevi</span><span class="sxs-lookup"><span data-stu-id="1f5f9-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="1f5f9-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1f5f9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1f5f9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f5f9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f5f9-105">Yalnızca bir sayı başka bir sayıdan küçük veya ona eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="1f5f9-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="1f5f9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1f5f9-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="1f5f9-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1f5f9-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1f5f9-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="1f5f9-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="1f5f9-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1f5f9-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1f5f9-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="1f5f9-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1f5f9-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1f5f9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1f5f9-112">`true` ve yalnızca, değerinden `a` küçükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="1f5f9-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1f5f9-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1f5f9-113">Remarks</span></span>

<span data-ttu-id="1f5f9-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="1f5f9-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```