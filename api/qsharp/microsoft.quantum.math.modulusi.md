---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 3f698a00b2c8d94b7cb3cca4f1721c659918f4a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732698"
---
# <a name="modulusi-function"></a><span data-ttu-id="966ff-102">ModulusI işlevi</span><span class="sxs-lookup"><span data-stu-id="966ff-102">ModulusI function</span></span>

<span data-ttu-id="966ff-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="966ff-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="966ff-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="966ff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="966ff-105">Modülden kaynaklanan kurallı bir şekilde `value` hesaplar `modulus` .</span><span class="sxs-lookup"><span data-stu-id="966ff-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="966ff-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="966ff-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="966ff-107">değer: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="966ff-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="966ff-108">Kalan değerin hesaplandığı değer</span><span class="sxs-lookup"><span data-stu-id="966ff-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="966ff-109">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="966ff-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="966ff-110">Resdues 'nin aldığı mod pozitif olmalıdır</span><span class="sxs-lookup"><span data-stu-id="966ff-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="966ff-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="966ff-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="966ff-112">0 ile 1 arasında $ ve `modulus - 1` `value - r` mod ile bölünebilen tamsayı $r</span><span class="sxs-lookup"><span data-stu-id="966ff-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="966ff-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="966ff-113">Remarks</span></span>

<span data-ttu-id="966ff-114">Bu işlev, işlecin `%` C# ' de nasıl davrandığı ile farklı davranır ve sonuçta `modulus - 1` , değer negatif olsa bile 0 ile her zaman pozitif bir tamsayı olur.</span><span class="sxs-lookup"><span data-stu-id="966ff-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>