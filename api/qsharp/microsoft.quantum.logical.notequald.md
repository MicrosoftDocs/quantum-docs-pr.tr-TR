---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 38f30309a4c27a5ef7e112a09a0efe3b5512d4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849043"
---
# <a name="notequald-function"></a><span data-ttu-id="0b79b-102">NotEqualD işlevi</span><span class="sxs-lookup"><span data-stu-id="0b79b-102">NotEqualD function</span></span>

<span data-ttu-id="0b79b-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0b79b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0b79b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b79b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b79b-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="0b79b-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="0b79b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0b79b-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="0b79b-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0b79b-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0b79b-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="0b79b-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="0b79b-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0b79b-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0b79b-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="0b79b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0b79b-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0b79b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0b79b-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="0b79b-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b79b-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0b79b-113">Remarks</span></span>

<span data-ttu-id="0b79b-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="0b79b-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualD(a, b);
```