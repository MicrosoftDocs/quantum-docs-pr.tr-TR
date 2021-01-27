---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 2247c1c1ae8b37b59e87c0c68b06fd1094c9003b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849193"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="cc3a7-102">GreaterThanL işlevi</span><span class="sxs-lookup"><span data-stu-id="cc3a7-102">GreaterThanL function</span></span>

<span data-ttu-id="cc3a7-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cc3a7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cc3a7-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc3a7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc3a7-105">Yalnızca bir sayı başka bir sayıdan daha büyükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="cc3a7-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="cc3a7-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="cc3a7-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="cc3a7-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cc3a7-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cc3a7-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="cc3a7-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="cc3a7-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cc3a7-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cc3a7-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="cc3a7-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cc3a7-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cc3a7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cc3a7-112">`true` yalnızca ve ' `a` den tamamen büyükse `b` .</span><span class="sxs-lookup"><span data-stu-id="cc3a7-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc3a7-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cc3a7-113">Remarks</span></span>

<span data-ttu-id="cc3a7-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="cc3a7-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanL(a, b);
```