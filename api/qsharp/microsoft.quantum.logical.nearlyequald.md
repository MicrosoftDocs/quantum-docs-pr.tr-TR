---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: Yaklaştığında Lyequald işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 246fad15c691a53fcc5be10f2c713672e0b54e6b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197475"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="c720d-102">Yaklaştığında Lyequald işlevi</span><span class="sxs-lookup"><span data-stu-id="c720d-102">NearlyEqualD function</span></span>

<span data-ttu-id="c720d-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c720d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c720d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c720d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c720d-105">Yalnızca iki giriş neredeyse eşitse (yani, 1e-12 toleransı dahilinde) true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="c720d-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c720d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c720d-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="c720d-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c720d-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c720d-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="c720d-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="c720d-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c720d-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c720d-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="c720d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c720d-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c720d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c720d-112">`true` ve yalnızca `a` neredeyse eşittir ise `b` .</span><span class="sxs-lookup"><span data-stu-id="c720d-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c720d-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c720d-113">Remarks</span></span>

<span data-ttu-id="c720d-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="c720d-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```