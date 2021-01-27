---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: Yaklaştığında Lyequald işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: fbbf1f7a59600ecc4a0a59d1c08cd0e1310d2d20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814365"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="4e1df-102">Yaklaştığında Lyequald işlevi</span><span class="sxs-lookup"><span data-stu-id="4e1df-102">NearlyEqualD function</span></span>

<span data-ttu-id="4e1df-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4e1df-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4e1df-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4e1df-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4e1df-105">Yalnızca iki giriş neredeyse eşitse (yani, 1e-12 toleransı dahilinde) true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="4e1df-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="4e1df-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4e1df-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="4e1df-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4e1df-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4e1df-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="4e1df-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="4e1df-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4e1df-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4e1df-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="4e1df-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4e1df-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4e1df-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4e1df-112">`true` ve yalnızca `a` neredeyse eşittir ise `b` .</span><span class="sxs-lookup"><span data-stu-id="4e1df-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e1df-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4e1df-113">Remarks</span></span>

<span data-ttu-id="4e1df-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="4e1df-114">The following are equivalent:</span></span>

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```