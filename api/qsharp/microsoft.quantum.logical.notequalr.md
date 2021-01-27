---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848510"
---
# <a name="notequalr-function"></a><span data-ttu-id="55408-102">NotEqualR işlevi</span><span class="sxs-lookup"><span data-stu-id="55408-102">NotEqualR function</span></span>

<span data-ttu-id="55408-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="55408-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="55408-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55408-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55408-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="55408-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="55408-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="55408-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="55408-107">y: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="55408-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="55408-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="55408-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="55408-109">b: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="55408-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="55408-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="55408-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="55408-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="55408-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="55408-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="55408-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="55408-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="55408-113">Remarks</span></span>

<span data-ttu-id="55408-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="55408-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```