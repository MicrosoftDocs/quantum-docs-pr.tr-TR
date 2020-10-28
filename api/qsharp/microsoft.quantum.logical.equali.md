---
uid: Microsoft.Quantum.Logical.EqualI
title: EqualI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 6b805e76217e033cb0135cf85bd8f37a3eb8636a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726078"
---
# <a name="equali-function"></a><span data-ttu-id="60d79-102">EqualI işlevi</span><span class="sxs-lookup"><span data-stu-id="60d79-102">EqualI function</span></span>

<span data-ttu-id="60d79-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="60d79-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="60d79-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="60d79-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="60d79-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="60d79-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="60d79-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="60d79-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="60d79-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="60d79-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="60d79-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="60d79-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="60d79-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="60d79-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="60d79-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="60d79-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="60d79-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="60d79-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="60d79-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="60d79-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="60d79-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="60d79-113">Remarks</span></span>

<span data-ttu-id="60d79-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="60d79-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```