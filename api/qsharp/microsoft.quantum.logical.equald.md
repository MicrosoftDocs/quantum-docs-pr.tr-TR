---
uid: Microsoft.Quantum.Logical.EqualD
title: EqualD işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d6731b293ba402f5cd43591d3c2bcd258e8ebe32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198155"
---
# <a name="equald-function"></a><span data-ttu-id="5eb48-102">EqualD işlevi</span><span class="sxs-lookup"><span data-stu-id="5eb48-102">EqualD function</span></span>

<span data-ttu-id="5eb48-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5eb48-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5eb48-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5eb48-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5eb48-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="5eb48-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="5eb48-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5eb48-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="5eb48-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5eb48-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5eb48-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="5eb48-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="5eb48-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5eb48-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5eb48-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="5eb48-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5eb48-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5eb48-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5eb48-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="5eb48-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5eb48-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5eb48-113">Remarks</span></span>

<span data-ttu-id="5eb48-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="5eb48-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```