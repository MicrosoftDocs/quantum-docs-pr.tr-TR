---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: ffd00d8086654a2d783a351fe254fb2ee35b9184
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726048"
---
# <a name="greaterthani-function"></a><span data-ttu-id="4a1de-102">GreaterThanI işlevi</span><span class="sxs-lookup"><span data-stu-id="4a1de-102">GreaterThanI function</span></span>

<span data-ttu-id="4a1de-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4a1de-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4a1de-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4a1de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4a1de-105">Yalnızca bir sayı başka bir sayıdan daha büyükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="4a1de-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="4a1de-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4a1de-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="4a1de-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4a1de-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4a1de-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="4a1de-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="4a1de-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4a1de-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4a1de-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="4a1de-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4a1de-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4a1de-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4a1de-112">`true` yalnızca ve ' `a` den tamamen büyükse `b` .</span><span class="sxs-lookup"><span data-stu-id="4a1de-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4a1de-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4a1de-113">Remarks</span></span>

<span data-ttu-id="4a1de-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="4a1de-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```