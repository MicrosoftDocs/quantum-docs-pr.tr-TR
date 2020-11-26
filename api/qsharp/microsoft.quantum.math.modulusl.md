---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 5c9a8ceceac5d2cdac6b82f7f74a85e9443382a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194942"
---
# <a name="modulusl-function"></a><span data-ttu-id="854e1-102">ModulusL işlevi</span><span class="sxs-lookup"><span data-stu-id="854e1-102">ModulusL function</span></span>

<span data-ttu-id="854e1-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="854e1-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="854e1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="854e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="854e1-105">Modülden kaynaklanan kurallı bir şekilde `value` hesaplar `modulus` .</span><span class="sxs-lookup"><span data-stu-id="854e1-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="854e1-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="854e1-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="854e1-107">değer: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="854e1-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="854e1-108">Kalan değerin hesaplandığı değer</span><span class="sxs-lookup"><span data-stu-id="854e1-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="854e1-109">mod: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="854e1-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="854e1-110">Resdues 'nin aldığı mod pozitif olmalıdır</span><span class="sxs-lookup"><span data-stu-id="854e1-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="854e1-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="854e1-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="854e1-112">0 ile 1 arasında $ ve `modulus - 1` `value - r` mod ile bölünebilen tamsayı $r</span><span class="sxs-lookup"><span data-stu-id="854e1-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="854e1-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="854e1-113">Remarks</span></span>

<span data-ttu-id="854e1-114">Bu işlev, işlecin `%` C# ' de nasıl davrandığı ile farklı davranır ve sonuçta `modulus - 1` , değer negatif olsa bile 0 ile her zaman pozitif bir tamsayı olur.</span><span class="sxs-lookup"><span data-stu-id="854e1-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>