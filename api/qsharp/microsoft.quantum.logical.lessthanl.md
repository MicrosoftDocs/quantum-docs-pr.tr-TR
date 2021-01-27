---
uid: Microsoft.Quantum.Logical.LessThanL
title: Lessbir l işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: d5753f9e1447fc1bd433703037fe44c86aaa659c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849143"
---
# <a name="lessthanl-function"></a><span data-ttu-id="8b7be-102">Lessbir l işlevi</span><span class="sxs-lookup"><span data-stu-id="8b7be-102">LessThanL function</span></span>

<span data-ttu-id="8b7be-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8b7be-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8b7be-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b7be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b7be-105">Yalnızca bir sayı başka bir sayıdan küçükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="8b7be-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="8b7be-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8b7be-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="8b7be-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="8b7be-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="8b7be-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="8b7be-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="8b7be-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="8b7be-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="8b7be-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="8b7be-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8b7be-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8b7be-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8b7be-112">`true` yalnızca ve ' `a` den tamamen küçükse `b` .</span><span class="sxs-lookup"><span data-stu-id="8b7be-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b7be-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8b7be-113">Remarks</span></span>

<span data-ttu-id="8b7be-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="8b7be-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanL(a, b);
```