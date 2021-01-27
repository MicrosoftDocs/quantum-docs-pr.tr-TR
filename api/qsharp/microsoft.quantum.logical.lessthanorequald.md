---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: Lesskıt Okarşılandığından ald işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 703b782efe9daccd4f6a339481d49ae9232123f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849133"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="21a04-102">Lesskıt Okarşılandığından ald işlevi</span><span class="sxs-lookup"><span data-stu-id="21a04-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="21a04-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="21a04-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="21a04-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="21a04-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="21a04-105">Yalnızca bir sayı başka bir sayıdan küçük veya ona eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="21a04-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="21a04-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="21a04-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="21a04-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="21a04-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="21a04-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="21a04-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="21a04-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="21a04-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="21a04-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="21a04-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="21a04-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="21a04-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="21a04-112">`true` ve yalnızca, değerinden `a` küçükse veya eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="21a04-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="21a04-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="21a04-113">Remarks</span></span>

<span data-ttu-id="21a04-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="21a04-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```