---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f88ae08f45c284f65151419c214705c74c3fadac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814497"
---
# <a name="notequali-function"></a><span data-ttu-id="be5ed-102">NotEqualI işlevi</span><span class="sxs-lookup"><span data-stu-id="be5ed-102">NotEqualI function</span></span>

<span data-ttu-id="be5ed-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="be5ed-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="be5ed-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="be5ed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="be5ed-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="be5ed-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="be5ed-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="be5ed-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="be5ed-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="be5ed-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="be5ed-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="be5ed-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="be5ed-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="be5ed-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="be5ed-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="be5ed-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="be5ed-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="be5ed-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="be5ed-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="be5ed-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="be5ed-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="be5ed-113">Remarks</span></span>

<span data-ttu-id="be5ed-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="be5ed-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualI(a, b);
```