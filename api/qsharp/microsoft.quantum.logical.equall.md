---
uid: Microsoft.Quantum.Logical.EqualL
title: EqualL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 395b8fedd3b3334939c2a4b5602ee19e0c6e34b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198121"
---
# <a name="equall-function"></a><span data-ttu-id="56027-102">EqualL işlevi</span><span class="sxs-lookup"><span data-stu-id="56027-102">EqualL function</span></span>

<span data-ttu-id="56027-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="56027-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="56027-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56027-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56027-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="56027-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="56027-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="56027-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="56027-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="56027-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="56027-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="56027-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="56027-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="56027-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="56027-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="56027-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="56027-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="56027-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="56027-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="56027-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="56027-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="56027-113">Remarks</span></span>

<span data-ttu-id="56027-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="56027-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```