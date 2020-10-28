---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Incrementphasebyınteger işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fb67455dadbc7a2f38880581f0e413a747faa8ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731487"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="3b1f5-102">Incrementphasebyınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="3b1f5-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="3b1f5-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3b1f5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3b1f5-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b1f5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b1f5-105">Bir işaretsiz hisse kaydetmeyi, bir klasik tamsayı tarafından, aşama döndürmeler kullanılarak arttırır.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="3b1f5-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3b1f5-106">Description</span></span>

<span data-ttu-id="3b1f5-107">`target`Bir işaretsiz tamsayı $x $ ' i küçük endian kodlamasıyla ve `increment` $a $ ' e eşit olarak kodluyor olduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="3b1f5-108">Daha sonra bu işlem, toplama işleminin gerçekleştiği modül $2 ^ n $, burada $n = \texttt{Length (Target!)} ' nin gerçekleştirildiği, Unitary $ \ket{x} \mapsto \ket{x + a} $ öğesini uygular $.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="3b1f5-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="3b1f5-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="3b1f5-110">artış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3b1f5-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3b1f5-111">Tarafından `target` arttırılan tamsayı.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="3b1f5-112">Hedef: [Phaselitttaendian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3b1f5-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="3b1f5-113">Hisse kaydı, Çift (QFT) temelinde küçük endian kodlaması kullanarak işaretsiz bir tamsayıyı kodlama.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3b1f5-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3b1f5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3b1f5-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3b1f5-115">Remarks</span></span>

<span data-ttu-id="3b1f5-116">Artış, hisse senedi kaydı değil, klasik bir sabit olduğundan, devreyi basitleştirdik.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="3b1f5-117">Devre diyagramı ve açıklama için [ sayfa 6 ' nın Arxıv: Quant-pH/0008033v1 sayfasında ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) yer alan şekle bakın.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="3b1f5-118">Referanslar</span><span class="sxs-lookup"><span data-stu-id="3b1f5-118">References</span></span>

- [<span data-ttu-id="3b1f5-119">*Thomas G. Draper* , arxıv: Quant-pH/0008033</span><span class="sxs-lookup"><span data-stu-id="3b1f5-119"> *Thomas G. Draper* , arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="3b1f5-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-120">See Also</span></span>

- [<span data-ttu-id="3b1f5-121">Microsoft. hisse. aritmetik. ıncrementbyınteger</span><span class="sxs-lookup"><span data-stu-id="3b1f5-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)