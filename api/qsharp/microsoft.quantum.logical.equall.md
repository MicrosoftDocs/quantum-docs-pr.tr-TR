---
uid: Microsoft.Quantum.Logical.EqualL
title: EqualL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 58086f40ea20b6f1a5fa6996e3a6703e2bf66306
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815983"
---
# <a name="equall-function"></a><span data-ttu-id="37e08-102">EqualL işlevi</span><span class="sxs-lookup"><span data-stu-id="37e08-102">EqualL function</span></span>

<span data-ttu-id="37e08-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="37e08-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="37e08-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37e08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37e08-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="37e08-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="37e08-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="37e08-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="37e08-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="37e08-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="37e08-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="37e08-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="37e08-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="37e08-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="37e08-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="37e08-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="37e08-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="37e08-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="37e08-112">`true` ve yalnızca `a` eşitse `b` .</span><span class="sxs-lookup"><span data-stu-id="37e08-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="37e08-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="37e08-113">Remarks</span></span>

<span data-ttu-id="37e08-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="37e08-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualL(a, b);
```