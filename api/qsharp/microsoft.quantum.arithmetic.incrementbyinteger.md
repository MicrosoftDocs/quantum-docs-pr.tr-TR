---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Incrementbyınteger işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fa5e75e91206aa5f33233c8a54d6e9e7ac2950e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222975"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="f2994-102">Incrementbyınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="f2994-102">IncrementByInteger operation</span></span>

<span data-ttu-id="f2994-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f2994-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f2994-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2994-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2994-105">Bir işaretsiz hisse kaydetmeyi, bir klasik tamsayı tarafından, aşama döndürmeler kullanılarak arttırır.</span><span class="sxs-lookup"><span data-stu-id="f2994-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f2994-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f2994-106">Description</span></span>

<span data-ttu-id="f2994-107">`target`Bir işaretsiz tamsayı $x $ ' i küçük endian kodlamasıyla ve `increment` $a $ ' e eşit olarak kodluyor olduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="f2994-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="f2994-108">Daha sonra bu işlem, toplama işleminin gerçekleştiği modül $2 ^ n $, burada $n = \texttt{Length (Target!)} ' nin gerçekleştirildiği, Unitary $ \ket{x} \mapsto \ket{x + a} $ öğesini uygular $.</span><span class="sxs-lookup"><span data-stu-id="f2994-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="f2994-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="f2994-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="f2994-110">artış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2994-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2994-111">Tarafından `target` arttırılan tamsayı.</span><span class="sxs-lookup"><span data-stu-id="f2994-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="f2994-112">Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f2994-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f2994-113">Hisse kaydı, küçük endian kodlaması kullanarak işaretsiz bir tamsayıyı kodlayan bir tamsayıdır.</span><span class="sxs-lookup"><span data-stu-id="f2994-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f2994-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2994-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

