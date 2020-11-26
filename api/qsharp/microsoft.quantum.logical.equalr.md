---
uid: Microsoft.Quantum.Logical.EqualR
title: EqualR işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d68b2f1a26bf318400d3c88b37d9aabcc38cbdfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198015"
---
# <a name="equalr-function"></a><span data-ttu-id="ee577-102">EqualR işlevi</span><span class="sxs-lookup"><span data-stu-id="ee577-102">EqualR function</span></span>

<span data-ttu-id="ee577-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ee577-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ee577-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee577-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee577-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="ee577-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="ee577-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ee577-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="ee577-107">y: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="ee577-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="ee577-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="ee577-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="ee577-109">b: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="ee577-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="ee577-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="ee577-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ee577-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ee577-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ee577-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="ee577-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee577-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ee577-113">Remarks</span></span>

<span data-ttu-id="ee577-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="ee577-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```