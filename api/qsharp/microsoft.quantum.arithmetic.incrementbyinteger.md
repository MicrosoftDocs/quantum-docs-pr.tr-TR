---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Incrementbyınteger işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 363d48d697e3b2dad4d4896e6b1e701864649d9b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731511"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="952e3-102">Incrementbyınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="952e3-102">IncrementByInteger operation</span></span>

<span data-ttu-id="952e3-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="952e3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="952e3-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="952e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="952e3-105">Bir işaretsiz hisse kaydetmeyi, bir klasik tamsayı tarafından, aşama döndürmeler kullanılarak arttırır.</span><span class="sxs-lookup"><span data-stu-id="952e3-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="952e3-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="952e3-106">Description</span></span>

<span data-ttu-id="952e3-107">`target`Bir işaretsiz tamsayı $x $ ' i küçük endian kodlamasıyla ve `increment` $a $ ' e eşit olarak kodluyor olduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="952e3-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="952e3-108">Daha sonra bu işlem, toplama işleminin gerçekleştiği modül $2 ^ n $, burada $n = \texttt{Length (Target!)} ' nin gerçekleştirildiği, Unitary $ \ket{x} \mapsto \ket{x + a} $ öğesini uygular $.</span><span class="sxs-lookup"><span data-stu-id="952e3-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="952e3-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="952e3-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="952e3-110">artış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="952e3-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="952e3-111">Tarafından `target` arttırılan tamsayı.</span><span class="sxs-lookup"><span data-stu-id="952e3-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="952e3-112">Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="952e3-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="952e3-113">Hisse kaydı, küçük endian kodlaması kullanarak işaretsiz bir tamsayıyı kodlayan bir tamsayıdır.</span><span class="sxs-lookup"><span data-stu-id="952e3-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="952e3-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="952e3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

