---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Incrementbymodularınteger işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 271033b32b0de6cf600dca82126dab19c2bb4f5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731503"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="220ed-102">Incrementbymodularınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="220ed-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="220ed-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="220ed-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="220ed-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="220ed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="220ed-105">Bir tamsayı sabiti ile bir qubit yazmacının modüler artışını gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="220ed-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="220ed-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="220ed-106">Description</span></span>

<span data-ttu-id="220ed-107">`increment`$A $, `modulus` $N $ ile $y $ ' de kodlanmış tamsayı olarak belirlememize izin verin `target` .</span><span class="sxs-lookup"><span data-stu-id="220ed-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="220ed-108">Sonra işlem şu dönüşümü gerçekleştirir: \begin{hizalaması} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{hizalaması} tamsayılar küçük endian biçiminde kodlanır.</span><span class="sxs-lookup"><span data-stu-id="220ed-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="220ed-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="220ed-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="220ed-110">artış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="220ed-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="220ed-111">$Y $ öğesine eklenecek $ $a tamsayı artışı.</span><span class="sxs-lookup"><span data-stu-id="220ed-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="220ed-112">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="220ed-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="220ed-113">Integer $N $ bu mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="220ed-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="220ed-114">Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="220ed-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="220ed-115">`LittleEndian`$A $ 'in eklendiği biçimde $y $ tamsayı `increment` .</span><span class="sxs-lookup"><span data-stu-id="220ed-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="220ed-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="220ed-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="220ed-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="220ed-117">Remarks</span></span>

<span data-ttu-id="220ed-118">Hedefin başlangıç değerinin $N $ ' den küçük olduğunu ve artış $a $ değerinin $N $ ' den küçük olduğunu varsayar.</span><span class="sxs-lookup"><span data-stu-id="220ed-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="220ed-119"><xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger>Aynı işlemi temelde uygulayan unutmayın `PhaseLittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="220ed-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="220ed-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="220ed-120">See Also</span></span>

- [<span data-ttu-id="220ed-121">Microsoft. hisse. aritmetik. ıncrementphasebymodularınteger</span><span class="sxs-lookup"><span data-stu-id="220ed-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)