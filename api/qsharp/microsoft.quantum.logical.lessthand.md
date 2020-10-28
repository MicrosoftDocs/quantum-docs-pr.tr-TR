---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 8cd274d5e299df2f556006baf7457d54aebcd071
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732927"
---
# <a name="lessthand-function"></a><span data-ttu-id="05b31-102">LessThanD işlevi</span><span class="sxs-lookup"><span data-stu-id="05b31-102">LessThanD function</span></span>

<span data-ttu-id="05b31-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="05b31-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="05b31-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05b31-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05b31-105">Yalnızca bir sayı başka bir sayıdan küçükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="05b31-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="05b31-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="05b31-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="05b31-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="05b31-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="05b31-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="05b31-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="05b31-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="05b31-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="05b31-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="05b31-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="05b31-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="05b31-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="05b31-112">`true` yalnızca ve ' `a` den tamamen küçükse `b` .</span><span class="sxs-lookup"><span data-stu-id="05b31-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="05b31-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="05b31-113">Remarks</span></span>

<span data-ttu-id="05b31-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="05b31-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```