---
uid: Microsoft.Quantum.Logical.NotEqualL
title: Not Quall işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: e138a8def30bc77499662ffa6bc214d0c6a38893
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197237"
---
# <a name="notequall-function"></a><span data-ttu-id="26df9-102">Not Quall işlevi</span><span class="sxs-lookup"><span data-stu-id="26df9-102">NotEqualL function</span></span>

<span data-ttu-id="26df9-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="26df9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="26df9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26df9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26df9-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="26df9-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="26df9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="26df9-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="26df9-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="26df9-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="26df9-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="26df9-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="26df9-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="26df9-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="26df9-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="26df9-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="26df9-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="26df9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="26df9-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="26df9-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="26df9-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="26df9-113">Remarks</span></span>

<span data-ttu-id="26df9-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="26df9-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```