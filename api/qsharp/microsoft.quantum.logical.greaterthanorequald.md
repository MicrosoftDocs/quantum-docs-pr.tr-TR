---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 98fa55c249f2ade414254d1bccda46a8602b828c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815861"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="4d7ff-102">GreaterThanOrEqualD işlevi</span><span class="sxs-lookup"><span data-stu-id="4d7ff-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="4d7ff-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4d7ff-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4d7ff-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d7ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d7ff-105">Yalnızca bir sayı başka bir sayıdan büyük veya buna eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="4d7ff-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="4d7ff-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4d7ff-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="4d7ff-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4d7ff-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4d7ff-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="4d7ff-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="4d7ff-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4d7ff-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4d7ff-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="4d7ff-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4d7ff-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4d7ff-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4d7ff-112">`true` ve yalnızca `a` değerinden büyükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="4d7ff-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4d7ff-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4d7ff-113">Remarks</span></span>

<span data-ttu-id="4d7ff-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="4d7ff-114">The following are equivalent:</span></span>

```qsharp
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```