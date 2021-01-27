---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: Incrementphasebymodülarınteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 4ba35010d56ad01c73cb563646dc8150842da12e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846587"
---
# <a name="incrementphasebymodularinteger-operation"></a><span data-ttu-id="658ca-102">Incrementphasebymodülarınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="658ca-102">IncrementPhaseByModularInteger operation</span></span>

<span data-ttu-id="658ca-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="658ca-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="658ca-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="658ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="658ca-105">Bir tamsayı sabiti ile bir qubit yazmacının modüler artışını gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="658ca-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="658ca-106">Description</span><span class="sxs-lookup"><span data-stu-id="658ca-106">Description</span></span>

<span data-ttu-id="658ca-107">`increment`$A $, `modulus` $N $ ile $y $ ' de kodlanmış tamsayı olarak belirlememize izin verin `target` .</span><span class="sxs-lookup"><span data-stu-id="658ca-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="658ca-108">Sonra işlem şu dönüşümü gerçekleştirir: \begin{hizalaması} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{hizalaması} tamsayılar, QFT 'de küçük endian biçiminde kodlanır.</span><span class="sxs-lookup"><span data-stu-id="658ca-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format in QFT basis.</span></span>

## <a name="input"></a><span data-ttu-id="658ca-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="658ca-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="658ca-110">artış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="658ca-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="658ca-111">$Y $ öğesine eklenecek $ $a tamsayı artışı.</span><span class="sxs-lookup"><span data-stu-id="658ca-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="658ca-112">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="658ca-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="658ca-113">Integer $N $ bu mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="658ca-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="658ca-114">Hedef: [Phaselitttaendian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="658ca-114">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="658ca-115">`increment`$A $ ' nin eklendiği, aşamalı olarak kodlanmış küçük endian biçimindeki tamsayı $y $.</span><span class="sxs-lookup"><span data-stu-id="658ca-115">Integer $y$ in phase-encoded little-endian format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="658ca-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="658ca-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="658ca-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="658ca-117">Remarks</span></span>

<span data-ttu-id="658ca-118">`target`En yüksek bit 0 olarak ayarlanmış olduğunu varsayar.</span><span class="sxs-lookup"><span data-stu-id="658ca-118">Assumes that `target` has the highest bit set to 0.</span></span>
<span data-ttu-id="658ca-119">Ayrıca hedefin değerinin $N $ ' den küçük olduğunu varsayar.</span><span class="sxs-lookup"><span data-stu-id="658ca-119">Also assumes that the value of target is less than $N$.</span></span>

<span data-ttu-id="658ca-120">Devre diyagramı ve açıklama için, [Arxıv: Quant-pH/, 5095v3 sayfa 5 sayfasında](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5)Şekil 5 ' i inceleyin.</span><span class="sxs-lookup"><span data-stu-id="658ca-120">For the circuit diagram and explanation see Figure 5 on [Page 5 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span></span>

## <a name="see-also"></a><span data-ttu-id="658ca-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="658ca-121">See Also</span></span>

- [<span data-ttu-id="658ca-122">Microsoft. hisse. aritmetik. ıncrementbymodularınteger</span><span class="sxs-lookup"><span data-stu-id="658ca-122">Microsoft.Quantum.Arithmetic.IncrementByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)