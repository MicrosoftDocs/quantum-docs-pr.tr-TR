---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: a59a9eca2941a44a70ec5a379b146ac459390bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732442"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="27da1-102">GreaterThanOrEqualL işlevi</span><span class="sxs-lookup"><span data-stu-id="27da1-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="27da1-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="27da1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="27da1-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27da1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27da1-105">Yalnızca bir sayı başka bir sayıdan büyük veya buna eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="27da1-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="27da1-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="27da1-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="27da1-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="27da1-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="27da1-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="27da1-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="27da1-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="27da1-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="27da1-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="27da1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="27da1-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="27da1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="27da1-112">`true` ve yalnızca `a` değerinden büyükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="27da1-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="27da1-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="27da1-113">Remarks</span></span>

<span data-ttu-id="27da1-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="27da1-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```