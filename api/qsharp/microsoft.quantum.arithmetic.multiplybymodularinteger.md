---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Multiplybymodularınteger işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730631"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="48059-102">Multiplybymodularınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="48059-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="48059-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="48059-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="48059-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48059-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48059-105">Bir qubit kaydındaki tamsayı sabiti ile modüler çarpma gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="48059-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="48059-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="48059-106">Description</span></span>

<span data-ttu-id="48059-107">`modulus`$N $ ve $a $ ile bu şekilde bir daha sunmamıza izin verin `constMultiplier` .</span><span class="sxs-lookup"><span data-stu-id="48059-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="48059-108">Bu işlem, şu eşleme tarafından hesaplama temelinde tanımlanan bir Unitary işlemi uygular: $ $ \begin{hizalaması} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{hizalaması} $ $ ile $0 $ ve $N-$1 arasında tüm $y $.</span><span class="sxs-lookup"><span data-stu-id="48059-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="48059-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="48059-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="48059-110">constMultiplier: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48059-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48059-111">Çarpanın çarpıldığı sabit.</span><span class="sxs-lookup"><span data-stu-id="48059-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="48059-112">Mod için ortak ana olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="48059-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="48059-113">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48059-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48059-114">Çarpma işlemi, mod gerçekleştirdi `modulus` .</span><span class="sxs-lookup"><span data-stu-id="48059-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="48059-115">çarpan: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="48059-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="48059-116">Bir sabit ile Çarpılmakta olan sayı.</span><span class="sxs-lookup"><span data-stu-id="48059-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="48059-117">Bu, küçük endian biçimindeki bir tamsayıyı kodlayan bir qubits dizisidir.</span><span class="sxs-lookup"><span data-stu-id="48059-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="48059-118">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48059-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="48059-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="48059-119">Remarks</span></span>

- <span data-ttu-id="48059-120">Devre diyagramı ve açıklama için, bkz. Şekil 7 [-Arxıv: Quant-pH/, 5095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="48059-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="48059-121">Bu işlem, [Arxıv: Quant-pH/, 5095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf) içindeki u ₐ 'a karşılık gelir</span><span class="sxs-lookup"><span data-stu-id="48059-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>