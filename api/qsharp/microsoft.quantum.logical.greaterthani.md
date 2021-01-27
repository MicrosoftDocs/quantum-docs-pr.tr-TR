---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 86fc8e927c292a2ea814ed80a33de42bffdb96b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815948"
---
# <a name="greaterthani-function"></a><span data-ttu-id="d3a32-102">GreaterThanI işlevi</span><span class="sxs-lookup"><span data-stu-id="d3a32-102">GreaterThanI function</span></span>

<span data-ttu-id="d3a32-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d3a32-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d3a32-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3a32-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3a32-105">Yalnızca bir sayı başka bir sayıdan daha büyükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="d3a32-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="d3a32-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d3a32-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d3a32-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3a32-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3a32-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="d3a32-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="d3a32-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3a32-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3a32-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="d3a32-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d3a32-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d3a32-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d3a32-112">`true` yalnızca ve ' `a` den tamamen büyükse `b` .</span><span class="sxs-lookup"><span data-stu-id="d3a32-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3a32-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d3a32-113">Remarks</span></span>

<span data-ttu-id="d3a32-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="d3a32-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanI(a, b);
```