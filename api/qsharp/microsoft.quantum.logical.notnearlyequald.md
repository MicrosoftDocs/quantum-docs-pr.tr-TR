---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: Notyaklaştığında Lyequald işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: 6e4cf3ec009f55ecc6345453c080520a3af6a8ef
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848480"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="fe292-102">Notyaklaştığında Lyequald işlevi</span><span class="sxs-lookup"><span data-stu-id="fe292-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="fe292-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fe292-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fe292-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe292-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe292-105">Yalnızca iki giriş neredeyse eşit değilse (yani, 1e-12 toleransı dahilinde değilse) true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="fe292-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="fe292-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="fe292-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="fe292-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fe292-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fe292-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="fe292-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="fe292-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fe292-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fe292-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="fe292-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fe292-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fe292-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fe292-112">`true` ve yalnızca `a` , için hemen eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="fe292-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe292-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="fe292-113">Remarks</span></span>

<span data-ttu-id="fe292-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="fe292-114">The following are equivalent:</span></span>

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```