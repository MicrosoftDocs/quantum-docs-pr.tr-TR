---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 91ab51180018a9b95a2f9010477c0a24f3a54617
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731290"
---
# <a name="equalb-function"></a><span data-ttu-id="ed5db-102">EqualB işlevi</span><span class="sxs-lookup"><span data-stu-id="ed5db-102">EqualB function</span></span>

<span data-ttu-id="ed5db-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ed5db-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ed5db-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed5db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed5db-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="ed5db-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="ed5db-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ed5db-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="ed5db-107">y: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ed5db-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ed5db-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="ed5db-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="ed5db-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ed5db-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ed5db-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="ed5db-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ed5db-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ed5db-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ed5db-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="ed5db-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed5db-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ed5db-113">Remarks</span></span>

<span data-ttu-id="ed5db-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="ed5db-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```