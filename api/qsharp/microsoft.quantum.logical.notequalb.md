---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: d5a9819bf3baa7c914487277fef308abbc8d25bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725987"
---
# <a name="notequalb-function"></a><span data-ttu-id="8af17-102">NotEqualB işlevi</span><span class="sxs-lookup"><span data-stu-id="8af17-102">NotEqualB function</span></span>

<span data-ttu-id="8af17-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8af17-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8af17-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8af17-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8af17-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="8af17-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="8af17-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8af17-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="8af17-107">y: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8af17-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8af17-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="8af17-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="8af17-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8af17-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8af17-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="8af17-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8af17-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8af17-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8af17-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="8af17-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8af17-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8af17-113">Remarks</span></span>

<span data-ttu-id="8af17-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="8af17-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```