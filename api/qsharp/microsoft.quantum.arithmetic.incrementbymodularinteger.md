---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Incrementbymodularınteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: f5bacef299ab0b3627e757abdcaa798cf9b2e7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846595"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="fefc2-102">Incrementbymodularınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="fefc2-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="fefc2-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fefc2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fefc2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fefc2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fefc2-105">Bir tamsayı sabiti ile bir qubit yazmacının modüler artışını gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="fefc2-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="fefc2-106">Description</span><span class="sxs-lookup"><span data-stu-id="fefc2-106">Description</span></span>

<span data-ttu-id="fefc2-107">`increment`$A $, `modulus` $N $ ile $y $ ' de kodlanmış tamsayı olarak belirlememize izin verin `target` .</span><span class="sxs-lookup"><span data-stu-id="fefc2-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="fefc2-108">Sonra işlem şu dönüşümü gerçekleştirir: \begin{hizalaması} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{hizalaması} tamsayılar küçük endian biçiminde kodlanır.</span><span class="sxs-lookup"><span data-stu-id="fefc2-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="fefc2-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="fefc2-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="fefc2-110">artış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fefc2-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fefc2-111">$Y $ öğesine eklenecek $ $a tamsayı artışı.</span><span class="sxs-lookup"><span data-stu-id="fefc2-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="fefc2-112">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fefc2-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fefc2-113">Integer $N $ bu mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="fefc2-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="fefc2-114">Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fefc2-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fefc2-115">`LittleEndian`$A $ 'in eklendiği biçimde $y $ tamsayı `increment` .</span><span class="sxs-lookup"><span data-stu-id="fefc2-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fefc2-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fefc2-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fefc2-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="fefc2-117">Remarks</span></span>

<span data-ttu-id="fefc2-118">Hedefin başlangıç değerinin $N $ ' den küçük olduğunu ve artış $a $ değerinin $N $ ' den küçük olduğunu varsayar.</span><span class="sxs-lookup"><span data-stu-id="fefc2-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="fefc2-119"><xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger>Aynı işlemi temelde uygulayan unutmayın `PhaseLittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="fefc2-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="fefc2-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fefc2-120">See Also</span></span>

- [<span data-ttu-id="fefc2-121">Microsoft. hisse. aritmetik. ıncrementphasebymodularınteger</span><span class="sxs-lookup"><span data-stu-id="fefc2-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)