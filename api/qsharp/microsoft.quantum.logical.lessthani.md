---
uid: Microsoft.Quantum.Logical.LessThanI
title: Lessdim i işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 5d5b17c8481ccf58b8e4fc4bb958e0adbf6d8f00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197781"
---
# <a name="lessthani-function"></a><span data-ttu-id="5288d-102">Lessdim i işlevi</span><span class="sxs-lookup"><span data-stu-id="5288d-102">LessThanI function</span></span>

<span data-ttu-id="5288d-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5288d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5288d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5288d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5288d-105">Yalnızca bir sayı başka bir sayıdan küçükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="5288d-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="5288d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5288d-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="5288d-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5288d-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5288d-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="5288d-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="5288d-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5288d-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5288d-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="5288d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5288d-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5288d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5288d-112">`true` yalnızca ve ' `a` den tamamen küçükse `b` .</span><span class="sxs-lookup"><span data-stu-id="5288d-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5288d-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5288d-113">Remarks</span></span>

<span data-ttu-id="5288d-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="5288d-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```