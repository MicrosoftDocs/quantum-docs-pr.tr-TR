---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 5536c009d6e78eac9ab2320b42aec7d2d82946eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197764"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="f4c51-102">GreaterThanOrEqualL işlevi</span><span class="sxs-lookup"><span data-stu-id="f4c51-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="f4c51-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f4c51-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f4c51-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4c51-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4c51-105">Yalnızca bir sayı başka bir sayıdan büyük veya buna eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="f4c51-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="f4c51-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f4c51-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="f4c51-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f4c51-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f4c51-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="f4c51-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="f4c51-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f4c51-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f4c51-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="f4c51-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f4c51-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f4c51-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f4c51-112">`true` ve yalnızca `a` değerinden büyükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="f4c51-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4c51-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f4c51-113">Remarks</span></span>

<span data-ttu-id="f4c51-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="f4c51-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```