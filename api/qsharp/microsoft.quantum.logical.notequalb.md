---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 7943411b662683df058213a9e4b8eb7c9329ff07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197390"
---
# <a name="notequalb-function"></a><span data-ttu-id="f4b59-102">NotEqualB işlevi</span><span class="sxs-lookup"><span data-stu-id="f4b59-102">NotEqualB function</span></span>

<span data-ttu-id="f4b59-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f4b59-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f4b59-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4b59-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4b59-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="f4b59-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="f4b59-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f4b59-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="f4b59-107">y: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f4b59-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f4b59-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="f4b59-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="f4b59-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f4b59-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f4b59-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="f4b59-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f4b59-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f4b59-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f4b59-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="f4b59-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4b59-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f4b59-113">Remarks</span></span>

<span data-ttu-id="f4b59-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="f4b59-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```