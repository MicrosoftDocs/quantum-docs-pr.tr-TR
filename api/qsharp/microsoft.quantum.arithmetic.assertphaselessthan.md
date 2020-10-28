---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: d003d83a84356ce52c5601135000813c7f119e4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731687"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="47dd6-102">AssertPhaseLessThan işlemi</span><span class="sxs-lookup"><span data-stu-id="47dd6-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="47dd6-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="47dd6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="47dd6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47dd6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47dd6-105">`number`Phaselitttaendian içinde kodlanan öğesinin küçüktür olduğunu onaylar `value` .</span><span class="sxs-lookup"><span data-stu-id="47dd6-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="47dd6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="47dd6-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="47dd6-107">değer: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="47dd6-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="47dd6-108">`number` bundan küçük olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="47dd6-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="47dd6-109">Sayı: [Phaselitttaendian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="47dd6-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="47dd6-110">İle karşılaştırılan işaretsiz tamsayı `value` .</span><span class="sxs-lookup"><span data-stu-id="47dd6-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="47dd6-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47dd6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="47dd6-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="47dd6-112">Remarks</span></span>

<span data-ttu-id="47dd6-113">Bu işlemin denetlenen sürümü denetimleri yoksayar.</span><span class="sxs-lookup"><span data-stu-id="47dd6-113">The controlled version of this operation ignores controls.</span></span>