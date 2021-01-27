---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: c1a513500c8a70bd7628976974387cba48162e80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849177"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="fdffd-102">GreaterThanOrEqualI işlevi</span><span class="sxs-lookup"><span data-stu-id="fdffd-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="fdffd-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fdffd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fdffd-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fdffd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fdffd-105">Yalnızca bir sayı başka bir sayıdan büyük veya buna eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="fdffd-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="fdffd-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="fdffd-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="fdffd-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fdffd-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fdffd-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="fdffd-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="fdffd-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fdffd-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fdffd-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="fdffd-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fdffd-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fdffd-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fdffd-112">`true` ve yalnızca `a` değerinden büyükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="fdffd-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fdffd-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="fdffd-113">Remarks</span></span>

<span data-ttu-id="fdffd-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="fdffd-114">The following are equivalent:</span></span>

```qsharp
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```