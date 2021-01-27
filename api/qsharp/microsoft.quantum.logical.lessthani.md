---
uid: Microsoft.Quantum.Logical.LessThanI
title: Lessdim i işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 69c3d7c414967b830c15189c895a2b34f409c7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815826"
---
# <a name="lessthani-function"></a><span data-ttu-id="7efb6-102">Lessdim i işlevi</span><span class="sxs-lookup"><span data-stu-id="7efb6-102">LessThanI function</span></span>

<span data-ttu-id="7efb6-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7efb6-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7efb6-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7efb6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7efb6-105">Yalnızca bir sayı başka bir sayıdan küçükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="7efb6-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="7efb6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7efb6-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="7efb6-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7efb6-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7efb6-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="7efb6-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="7efb6-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7efb6-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7efb6-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="7efb6-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7efb6-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7efb6-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7efb6-112">`true` yalnızca ve ' `a` den tamamen küçükse `b` .</span><span class="sxs-lookup"><span data-stu-id="7efb6-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7efb6-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7efb6-113">Remarks</span></span>

<span data-ttu-id="7efb6-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="7efb6-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanI(a, b);
```