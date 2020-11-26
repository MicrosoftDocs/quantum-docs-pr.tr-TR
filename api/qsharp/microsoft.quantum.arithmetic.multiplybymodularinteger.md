---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Multiplybymodularınteger işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 080414d208a2a0c114857db8e93efb4cd74a4d8d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222584"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="6bf46-102">Multiplybymodularınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="6bf46-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="6bf46-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6bf46-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6bf46-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6bf46-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6bf46-105">Bir qubit kaydındaki tamsayı sabiti ile modüler çarpma gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="6bf46-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6bf46-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6bf46-106">Description</span></span>

<span data-ttu-id="6bf46-107">`modulus`$N $ ve $a $ ile bu şekilde bir daha sunmamıza izin verin `constMultiplier` .</span><span class="sxs-lookup"><span data-stu-id="6bf46-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="6bf46-108">Bu işlem, şu eşleme tarafından hesaplama temelinde tanımlanan bir Unitary işlemi uygular: $ $ \begin{hizalaması} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{hizalaması} $ $ ile $0 $ ve $N-$1 arasında tüm $y $.</span><span class="sxs-lookup"><span data-stu-id="6bf46-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="6bf46-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="6bf46-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="6bf46-110">constMultiplier: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6bf46-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6bf46-111">Çarpanın çarpıldığı sabit.</span><span class="sxs-lookup"><span data-stu-id="6bf46-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="6bf46-112">Mod için ortak ana olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="6bf46-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="6bf46-113">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6bf46-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6bf46-114">Çarpma işlemi, mod gerçekleştirdi `modulus` .</span><span class="sxs-lookup"><span data-stu-id="6bf46-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="6bf46-115">çarpan: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6bf46-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6bf46-116">Bir sabit ile Çarpılmakta olan sayı.</span><span class="sxs-lookup"><span data-stu-id="6bf46-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="6bf46-117">Bu, küçük endian biçimindeki bir tamsayıyı kodlayan bir qubits dizisidir.</span><span class="sxs-lookup"><span data-stu-id="6bf46-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6bf46-118">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bf46-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6bf46-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6bf46-119">Remarks</span></span>

- <span data-ttu-id="6bf46-120">Devre diyagramı ve açıklama için, bkz. Şekil 7 [-Arxıv: Quant-pH/, 5095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="6bf46-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="6bf46-121">Bu işlem, [Arxıv: Quant-pH/, 5095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf) içindeki u ₐ 'a karşılık gelir</span><span class="sxs-lookup"><span data-stu-id="6bf46-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>