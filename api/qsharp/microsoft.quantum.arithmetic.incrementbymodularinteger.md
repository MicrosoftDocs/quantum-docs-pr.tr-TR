---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Incrementbymodularınteger işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 8a02d22facce8f58180752b6d063ac55d75ca537
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222958"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="b6945-102">Incrementbymodularınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="b6945-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="b6945-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b6945-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b6945-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6945-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6945-105">Bir tamsayı sabiti ile bir qubit yazmacının modüler artışını gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="b6945-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b6945-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b6945-106">Description</span></span>

<span data-ttu-id="b6945-107">`increment`$A $, `modulus` $N $ ile $y $ ' de kodlanmış tamsayı olarak belirlememize izin verin `target` .</span><span class="sxs-lookup"><span data-stu-id="b6945-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="b6945-108">Sonra işlem şu dönüşümü gerçekleştirir: \begin{hizalaması} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{hizalaması} tamsayılar küçük endian biçiminde kodlanır.</span><span class="sxs-lookup"><span data-stu-id="b6945-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="b6945-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="b6945-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="b6945-110">artış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6945-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b6945-111">$Y $ öğesine eklenecek $ $a tamsayı artışı.</span><span class="sxs-lookup"><span data-stu-id="b6945-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="b6945-112">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6945-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b6945-113">Integer $N $ bu mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="b6945-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="b6945-114">Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b6945-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b6945-115">`LittleEndian`$A $ 'in eklendiği biçimde $y $ tamsayı `increment` .</span><span class="sxs-lookup"><span data-stu-id="b6945-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b6945-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6945-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b6945-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b6945-117">Remarks</span></span>

<span data-ttu-id="b6945-118">Hedefin başlangıç değerinin $N $ ' den küçük olduğunu ve artış $a $ değerinin $N $ ' den küçük olduğunu varsayar.</span><span class="sxs-lookup"><span data-stu-id="b6945-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="b6945-119"><xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger>Aynı işlemi temelde uygulayan unutmayın `PhaseLittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="b6945-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6945-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b6945-120">See Also</span></span>

- [<span data-ttu-id="b6945-121">Microsoft. hisse. aritmetik. ıncrementphasebymodularınteger</span><span class="sxs-lookup"><span data-stu-id="b6945-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)