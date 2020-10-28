---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 292599c18d2aac44cef8f0eecca38eb1fbe22061
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732930"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="96513-102">GreaterThanOrEqualI işlevi</span><span class="sxs-lookup"><span data-stu-id="96513-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="96513-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="96513-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="96513-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96513-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96513-105">Yalnızca bir sayı başka bir sayıdan büyük veya buna eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="96513-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="96513-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="96513-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="96513-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96513-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96513-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="96513-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="96513-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96513-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96513-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="96513-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="96513-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="96513-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="96513-112">`true` ve yalnızca `a` değerinden büyükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="96513-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="96513-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="96513-113">Remarks</span></span>

<span data-ttu-id="96513-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="96513-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```