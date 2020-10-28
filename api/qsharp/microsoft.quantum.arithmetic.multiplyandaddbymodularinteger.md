---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: Multiplyandadddbymodülarınteger işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 3f85f6aaea1d6f8095709c6f387322df7a5e047c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730642"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="191ec-102">Multiplyandadddbymodülarınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="191ec-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="191ec-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="191ec-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="191ec-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="191ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="191ec-105">Bir qubit kaydındaki modüler çarpma ve tamsayı sabitlerine göre ekleme gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="191ec-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="191ec-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="191ec-106">Description</span></span>

<span data-ttu-id="191ec-107">Verilen bir mod $N $, sabit çarpanı $a $ ve summand $y $ için $ $ \begin{hizalaması} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{hizalaması} $ $ eşlemesini uygular.</span><span class="sxs-lookup"><span data-stu-id="191ec-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="191ec-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="191ec-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="191ec-109">constMultiplier: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="191ec-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="191ec-110">Her temel durum etiketine eklenecek bir tamsayı $a.</span><span class="sxs-lookup"><span data-stu-id="191ec-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="191ec-111">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="191ec-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="191ec-112">Mod $N $, ne kadar toplama ve çarpma işlemi yapılır.</span><span class="sxs-lookup"><span data-stu-id="191ec-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="191ec-113">çarpan: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="191ec-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="191ec-114">Her bir temel durum etiketine eklenecek olan işaretsiz bir tamsayıyı temsil eden bir hisse kaydı `summand` .</span><span class="sxs-lookup"><span data-stu-id="191ec-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="191ec-115">summand: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="191ec-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="191ec-116">Bu işlem için hedef olarak kullanılacak işaretsiz bir tamsayıyı temsil eden bir hisse kaydı.</span><span class="sxs-lookup"><span data-stu-id="191ec-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="191ec-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="191ec-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="191ec-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="191ec-118">Remarks</span></span>

- <span data-ttu-id="191ec-119">Devre diyagramı ve açıklama için bkz. Şekil 6 ' da [Arxıv: Quant-pH/, 5095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span><span class="sxs-lookup"><span data-stu-id="191ec-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="191ec-120">Bu işlem, [Arxıv: Quant-pH/, 5095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf) içindeki cmult (a) mod (N) öğesine karşılık gelir</span><span class="sxs-lookup"><span data-stu-id="191ec-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="191ec-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="191ec-121">See Also</span></span>

- [<span data-ttu-id="191ec-122">Microsoft. hisse. aritmetik. Multiplyandadddphasebymodularınteger</span><span class="sxs-lookup"><span data-stu-id="191ec-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)