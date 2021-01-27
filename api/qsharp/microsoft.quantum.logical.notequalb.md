---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 9f362b9e08f8a798bf7f7d9c323fee6576dccd9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814415"
---
# <a name="notequalb-function"></a><span data-ttu-id="d4f88-102">NotEqualB işlevi</span><span class="sxs-lookup"><span data-stu-id="d4f88-102">NotEqualB function</span></span>

<span data-ttu-id="d4f88-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d4f88-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d4f88-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4f88-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4f88-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="d4f88-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="d4f88-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d4f88-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="d4f88-107">y: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d4f88-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d4f88-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="d4f88-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="d4f88-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d4f88-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d4f88-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="d4f88-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d4f88-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d4f88-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d4f88-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="d4f88-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d4f88-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d4f88-113">Remarks</span></span>

<span data-ttu-id="d4f88-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="d4f88-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualB(a, b);
```