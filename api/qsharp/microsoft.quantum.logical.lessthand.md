---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 7135ed4b3414d143f5020496ae524bf89980a8a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849168"
---
# <a name="lessthand-function"></a><span data-ttu-id="81683-102">LessThanD işlevi</span><span class="sxs-lookup"><span data-stu-id="81683-102">LessThanD function</span></span>

<span data-ttu-id="81683-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="81683-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="81683-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="81683-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="81683-105">Yalnızca bir sayı başka bir sayıdan küçükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="81683-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="81683-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="81683-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="81683-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81683-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="81683-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="81683-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="81683-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81683-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="81683-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="81683-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="81683-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="81683-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="81683-112">`true` yalnızca ve ' `a` den tamamen küçükse `b` .</span><span class="sxs-lookup"><span data-stu-id="81683-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="81683-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="81683-113">Remarks</span></span>

<span data-ttu-id="81683-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="81683-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanD(a, b);
```