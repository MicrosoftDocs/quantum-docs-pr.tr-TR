---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4599d7125dbc67547af454183f620e8d84f2caf7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197254"
---
# <a name="notequald-function"></a><span data-ttu-id="652de-102">NotEqualD işlevi</span><span class="sxs-lookup"><span data-stu-id="652de-102">NotEqualD function</span></span>

<span data-ttu-id="652de-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="652de-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="652de-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="652de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="652de-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="652de-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="652de-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="652de-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="652de-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="652de-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="652de-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="652de-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="652de-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="652de-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="652de-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="652de-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="652de-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="652de-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="652de-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="652de-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="652de-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="652de-113">Remarks</span></span>

<span data-ttu-id="652de-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="652de-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```