---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 676defa7824e53578504c559c6d8f24b2ffc1a88
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726648"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="7983d-102">GreaterThanL işlevi</span><span class="sxs-lookup"><span data-stu-id="7983d-102">GreaterThanL function</span></span>

<span data-ttu-id="7983d-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7983d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7983d-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7983d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7983d-105">Yalnızca bir sayı başka bir sayıdan daha büyükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="7983d-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="7983d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7983d-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="7983d-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7983d-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7983d-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="7983d-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="7983d-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7983d-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7983d-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="7983d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7983d-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7983d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7983d-112">`true` yalnızca ve ' `a` den tamamen büyükse `b` .</span><span class="sxs-lookup"><span data-stu-id="7983d-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7983d-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7983d-113">Remarks</span></span>

<span data-ttu-id="7983d-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="7983d-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```