---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: c23d85cf513bb6d37e67260eeeb3b81b42e6771a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198036"
---
# <a name="greaterthand-function"></a><span data-ttu-id="7bf8d-102">GreaterThanD işlevi</span><span class="sxs-lookup"><span data-stu-id="7bf8d-102">GreaterThanD function</span></span>

<span data-ttu-id="7bf8d-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7bf8d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7bf8d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7bf8d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7bf8d-105">Yalnızca bir sayı başka bir sayıdan daha büyükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="7bf8d-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="7bf8d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7bf8d-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="7bf8d-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7bf8d-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7bf8d-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="7bf8d-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="7bf8d-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7bf8d-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7bf8d-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="7bf8d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7bf8d-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7bf8d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7bf8d-112">`true` yalnızca ve ' `a` den tamamen büyükse `b` .</span><span class="sxs-lookup"><span data-stu-id="7bf8d-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7bf8d-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7bf8d-113">Remarks</span></span>

<span data-ttu-id="7bf8d-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="7bf8d-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```