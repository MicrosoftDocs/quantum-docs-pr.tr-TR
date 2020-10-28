---
uid: Microsoft.Quantum.Logical.NotEqualL
title: Not Quall işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f1d36c284293519e75e6c30ac64679c7bdf4609c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725975"
---
# <a name="notequall-function"></a><span data-ttu-id="f55bf-102">Not Quall işlevi</span><span class="sxs-lookup"><span data-stu-id="f55bf-102">NotEqualL function</span></span>

<span data-ttu-id="f55bf-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f55bf-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f55bf-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f55bf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f55bf-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="f55bf-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="f55bf-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f55bf-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="f55bf-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f55bf-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f55bf-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="f55bf-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="f55bf-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f55bf-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f55bf-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="f55bf-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f55bf-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f55bf-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f55bf-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="f55bf-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f55bf-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f55bf-113">Remarks</span></span>

<span data-ttu-id="f55bf-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="f55bf-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```