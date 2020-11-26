---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: b566f5ba8548eadeecf63a1e91956d936e7e9a20
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198478"
---
# <a name="equalb-function"></a><span data-ttu-id="e75c1-102">EqualB işlevi</span><span class="sxs-lookup"><span data-stu-id="e75c1-102">EqualB function</span></span>

<span data-ttu-id="e75c1-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e75c1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e75c1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e75c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e75c1-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="e75c1-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="e75c1-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e75c1-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="e75c1-107">y: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e75c1-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e75c1-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="e75c1-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="e75c1-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e75c1-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e75c1-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="e75c1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e75c1-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e75c1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e75c1-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="e75c1-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e75c1-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e75c1-113">Remarks</span></span>

<span data-ttu-id="e75c1-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="e75c1-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```