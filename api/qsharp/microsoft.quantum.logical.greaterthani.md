---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 06cae04150f9f0164b06a4e3d4bb78242b41dc0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198019"
---
# <a name="greaterthani-function"></a><span data-ttu-id="47142-102">GreaterThanI işlevi</span><span class="sxs-lookup"><span data-stu-id="47142-102">GreaterThanI function</span></span>

<span data-ttu-id="47142-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="47142-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="47142-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47142-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47142-105">Yalnızca bir sayı başka bir sayıdan daha büyükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="47142-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="47142-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="47142-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="47142-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="47142-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="47142-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="47142-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="47142-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="47142-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="47142-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="47142-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="47142-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="47142-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="47142-112">`true` yalnızca ve ' `a` den tamamen büyükse `b` .</span><span class="sxs-lookup"><span data-stu-id="47142-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="47142-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="47142-113">Remarks</span></span>

<span data-ttu-id="47142-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="47142-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```