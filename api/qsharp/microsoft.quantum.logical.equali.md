---
uid: Microsoft.Quantum.Logical.EqualI
title: EqualI işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 87cf00ea8bb738cda30092b3d80940291beb1fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816743"
---
# <a name="equali-function"></a><span data-ttu-id="a9943-102">EqualI işlevi</span><span class="sxs-lookup"><span data-stu-id="a9943-102">EqualI function</span></span>

<span data-ttu-id="a9943-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a9943-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a9943-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a9943-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a9943-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="a9943-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="a9943-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a9943-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a9943-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a9943-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a9943-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="a9943-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="a9943-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a9943-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a9943-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="a9943-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a9943-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a9943-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a9943-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="a9943-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a9943-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a9943-113">Remarks</span></span>

<span data-ttu-id="a9943-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="a9943-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualI(a, b);
```