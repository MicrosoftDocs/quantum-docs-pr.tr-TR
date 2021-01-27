---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842738"
---
# <a name="modulusl-function"></a><span data-ttu-id="041ed-102">ModulusL işlevi</span><span class="sxs-lookup"><span data-stu-id="041ed-102">ModulusL function</span></span>

<span data-ttu-id="041ed-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="041ed-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="041ed-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="041ed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="041ed-105">Modülden kaynaklanan kurallı bir şekilde `value` hesaplar `modulus` .</span><span class="sxs-lookup"><span data-stu-id="041ed-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="041ed-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="041ed-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="041ed-107">değer: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="041ed-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="041ed-108">Kalan değerin hesaplandığı değer</span><span class="sxs-lookup"><span data-stu-id="041ed-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="041ed-109">mod: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="041ed-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="041ed-110">Resdues 'nin aldığı mod pozitif olmalıdır</span><span class="sxs-lookup"><span data-stu-id="041ed-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="041ed-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="041ed-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="041ed-112">0 ile 1 arasında $ ve `modulus - 1` `value - r` mod ile bölünebilen tamsayı $r</span><span class="sxs-lookup"><span data-stu-id="041ed-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="041ed-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="041ed-113">Remarks</span></span>

<span data-ttu-id="041ed-114">Bu işlev, işlecin `%` C# ' de nasıl davrandığı ve sonuç olarak 0 ile arasında negatif olmayan bir tamsayı ve `modulus - 1` değer negatif olsa bile</span><span class="sxs-lookup"><span data-stu-id="041ed-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>