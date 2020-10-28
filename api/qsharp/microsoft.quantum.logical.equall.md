---
uid: Microsoft.Quantum.Logical.EqualL
title: EqualL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f0a2bfa866068746e9c6e249573eb61c0d08c0f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726072"
---
# <a name="equall-function"></a><span data-ttu-id="4acea-102">EqualL işlevi</span><span class="sxs-lookup"><span data-stu-id="4acea-102">EqualL function</span></span>

<span data-ttu-id="4acea-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4acea-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4acea-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4acea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4acea-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="4acea-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="4acea-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4acea-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4acea-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4acea-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4acea-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="4acea-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4acea-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4acea-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4acea-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="4acea-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4acea-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4acea-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4acea-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="4acea-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4acea-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4acea-113">Remarks</span></span>

<span data-ttu-id="4acea-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="4acea-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```