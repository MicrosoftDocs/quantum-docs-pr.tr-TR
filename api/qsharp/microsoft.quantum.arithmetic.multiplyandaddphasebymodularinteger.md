---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Multiplyandadddphasebymodularınteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: b1214acc2cafc3fede9fcb6663a435c0b1d2cf4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843072"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="9d54d-102">Multiplyandadddphasebymodularınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="9d54d-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="9d54d-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9d54d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9d54d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d54d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d54d-105">Multiplyandavddbymodularınteger ile aynıdır, ancak summve tamsayıların QFT temelinde kodladığını varsayar.</span><span class="sxs-lookup"><span data-stu-id="9d54d-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9d54d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9d54d-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="9d54d-107">constMultiplier: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9d54d-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9d54d-108">Her temel durum etiketine eklenecek bir tamsayı $a.</span><span class="sxs-lookup"><span data-stu-id="9d54d-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="9d54d-109">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9d54d-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9d54d-110">Mod $N $, ne kadar toplama ve çarpma işlemi yapılır.</span><span class="sxs-lookup"><span data-stu-id="9d54d-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="9d54d-111">çarpan: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9d54d-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9d54d-112">Her bir temel durum etiketine eklenecek olan işaretsiz bir tamsayıyı temsil eden bir hisse kaydı `summand` .</span><span class="sxs-lookup"><span data-stu-id="9d54d-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="9d54d-113">phaseSummand: [Phaselitttaendian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9d54d-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="9d54d-114">Bu işlem için hedef olarak kullanılacak işaretsiz bir tamsayıyı temsil eden bir hisse kaydı.</span><span class="sxs-lookup"><span data-stu-id="9d54d-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d54d-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d54d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9d54d-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9d54d-116">Remarks</span></span>

<span data-ttu-id="9d54d-117">`phaseSummand`En yüksek bit 0 olarak ayarlanmış olduğunu varsayar.</span><span class="sxs-lookup"><span data-stu-id="9d54d-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="9d54d-118">Ayrıca değerinin `phaseSummand` $N $ değerinden küçük olduğunu varsayar.</span><span class="sxs-lookup"><span data-stu-id="9d54d-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d54d-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9d54d-119">See Also</span></span>

- [<span data-ttu-id="9d54d-120">Microsoft. hisse. aritmetik. Multiplyandadddbymodularınteger</span><span class="sxs-lookup"><span data-stu-id="9d54d-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)