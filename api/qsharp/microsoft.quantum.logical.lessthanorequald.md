---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: Lesskıt Okarşılandığından ald işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 7b0e9da379bd67eb78a80e7a535a15dcb8ba85c7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726035"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="25a5c-102">Lesskıt Okarşılandığından ald işlevi</span><span class="sxs-lookup"><span data-stu-id="25a5c-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="25a5c-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="25a5c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="25a5c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25a5c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25a5c-105">Yalnızca bir sayı başka bir sayıdan küçük veya ona eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="25a5c-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="25a5c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="25a5c-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="25a5c-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="25a5c-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="25a5c-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="25a5c-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="25a5c-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="25a5c-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="25a5c-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="25a5c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="25a5c-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="25a5c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="25a5c-112">`true` ve yalnızca, değerinden `a` küçükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="25a5c-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="25a5c-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="25a5c-113">Remarks</span></span>

<span data-ttu-id="25a5c-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="25a5c-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```