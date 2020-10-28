---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 20414e80e08993a18331a8f0b385a1e4cc1255b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726059"
---
# <a name="greaterthand-function"></a><span data-ttu-id="733fb-102">GreaterThanD işlevi</span><span class="sxs-lookup"><span data-stu-id="733fb-102">GreaterThanD function</span></span>

<span data-ttu-id="733fb-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="733fb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="733fb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="733fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="733fb-105">Yalnızca bir sayı başka bir sayıdan daha büyükse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="733fb-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="733fb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="733fb-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="733fb-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="733fb-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="733fb-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="733fb-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="733fb-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="733fb-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="733fb-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="733fb-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="733fb-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="733fb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="733fb-112">`true` yalnızca ve ' `a` den tamamen büyükse `b` .</span><span class="sxs-lookup"><span data-stu-id="733fb-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="733fb-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="733fb-113">Remarks</span></span>

<span data-ttu-id="733fb-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="733fb-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```