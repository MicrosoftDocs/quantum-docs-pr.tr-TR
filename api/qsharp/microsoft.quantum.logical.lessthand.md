---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 40f059e49affbb1b5af7dc349f6ee53dfb357873
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197747"
---
# <a name="lessthand-function"></a><span data-ttu-id="94ea5-102">LessThanD işlevi</span><span class="sxs-lookup"><span data-stu-id="94ea5-102">LessThanD function</span></span>

<span data-ttu-id="94ea5-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="94ea5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="94ea5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94ea5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94ea5-105">Yalnızca bir sayı başka bir sayıdan küçükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="94ea5-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="94ea5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="94ea5-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="94ea5-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="94ea5-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="94ea5-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="94ea5-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="94ea5-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="94ea5-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="94ea5-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="94ea5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="94ea5-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="94ea5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="94ea5-112">`true` yalnızca ve ' `a` den tamamen küçükse `b` .</span><span class="sxs-lookup"><span data-stu-id="94ea5-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="94ea5-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="94ea5-113">Remarks</span></span>

<span data-ttu-id="94ea5-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="94ea5-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```