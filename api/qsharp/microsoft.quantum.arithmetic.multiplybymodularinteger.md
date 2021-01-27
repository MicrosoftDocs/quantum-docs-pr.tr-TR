---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Multiplybymodularınteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: bd4e0ad6c5bad779d9a31139690021fd9fcda210
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846503"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="cb34e-102">Multiplybymodularınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="cb34e-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="cb34e-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cb34e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cb34e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb34e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb34e-105">Bir qubit kaydındaki tamsayı sabiti ile modüler çarpma gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="cb34e-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="cb34e-106">Description</span><span class="sxs-lookup"><span data-stu-id="cb34e-106">Description</span></span>

<span data-ttu-id="cb34e-107">`modulus`$N $ ve $a $ ile bu şekilde bir daha sunmamıza izin verin `constMultiplier` .</span><span class="sxs-lookup"><span data-stu-id="cb34e-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="cb34e-108">Bu işlem, şu eşleme tarafından hesaplama temelinde tanımlanan bir Unitary işlemi uygular: $ $ \begin{hizalaması} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{hizalaması} $ $ ile $0 $ ve $N-$1 arasında tüm $y $.</span><span class="sxs-lookup"><span data-stu-id="cb34e-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="cb34e-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="cb34e-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="cb34e-110">constMultiplier: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cb34e-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cb34e-111">Çarpanın çarpıldığı sabit.</span><span class="sxs-lookup"><span data-stu-id="cb34e-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="cb34e-112">Mod için ortak ana olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="cb34e-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="cb34e-113">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cb34e-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cb34e-114">Çarpma işlemi, mod gerçekleştirdi `modulus` .</span><span class="sxs-lookup"><span data-stu-id="cb34e-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="cb34e-115">çarpan: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cb34e-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cb34e-116">Bir sabit ile Çarpılmakta olan sayı.</span><span class="sxs-lookup"><span data-stu-id="cb34e-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="cb34e-117">Bu, küçük endian biçimindeki bir tamsayıyı kodlayan bir qubits dizisidir.</span><span class="sxs-lookup"><span data-stu-id="cb34e-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb34e-118">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb34e-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cb34e-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cb34e-119">Remarks</span></span>

- <span data-ttu-id="cb34e-120">Devre diyagramı ve açıklama için, bkz. Şekil 7 [-Arxıv: Quant-pH/, 5095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="cb34e-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="cb34e-121">Bu işlem, [Arxıv: Quant-pH/, 5095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf) içindeki u ₐ 'a karşılık gelir</span><span class="sxs-lookup"><span data-stu-id="cb34e-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>