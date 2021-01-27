---
uid: Microsoft.Quantum.Logical.EqualD
title: EqualD işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f8a24d7bfb9b4f7b8b0e1f68a94bfb341716b024
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816861"
---
# <a name="equald-function"></a><span data-ttu-id="37188-102">EqualD işlevi</span><span class="sxs-lookup"><span data-stu-id="37188-102">EqualD function</span></span>

<span data-ttu-id="37188-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="37188-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="37188-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37188-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37188-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="37188-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="37188-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="37188-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="37188-107">y: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="37188-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="37188-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="37188-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="37188-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="37188-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="37188-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="37188-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="37188-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="37188-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="37188-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="37188-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="37188-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="37188-113">Remarks</span></span>

<span data-ttu-id="37188-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="37188-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualD(a, b);
```