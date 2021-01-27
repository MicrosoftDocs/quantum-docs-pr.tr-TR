---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 7bad044db9e2229c85cb3909dc4802bceaee6382
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847299"
---
# <a name="modulusi-function"></a><span data-ttu-id="7a64a-102">ModulusI işlevi</span><span class="sxs-lookup"><span data-stu-id="7a64a-102">ModulusI function</span></span>

<span data-ttu-id="7a64a-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7a64a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7a64a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7a64a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7a64a-105">Modülden kaynaklanan kurallı bir şekilde `value` hesaplar `modulus` .</span><span class="sxs-lookup"><span data-stu-id="7a64a-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="7a64a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7a64a-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="7a64a-107">değer: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a64a-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a64a-108">Kalan değerin hesaplandığı değer</span><span class="sxs-lookup"><span data-stu-id="7a64a-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="7a64a-109">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a64a-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a64a-110">Resdues 'nin aldığı mod pozitif olmalıdır</span><span class="sxs-lookup"><span data-stu-id="7a64a-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="7a64a-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a64a-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a64a-112">0 ile 1 arasında $ ve `modulus - 1` `value - r` mod ile bölünebilen tamsayı $r</span><span class="sxs-lookup"><span data-stu-id="7a64a-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="7a64a-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7a64a-113">Remarks</span></span>

<span data-ttu-id="7a64a-114">Bu işlev, işlecin `%` C# ' de nasıl davrandığı ve sonuç olarak 0 ile arasında negatif olmayan bir tamsayı ve `modulus - 1` değer negatif olsa bile</span><span class="sxs-lookup"><span data-stu-id="7a64a-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>