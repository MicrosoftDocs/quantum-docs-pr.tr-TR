---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Measureınteger işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731415"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="d570e-102">Measureınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="d570e-102">MeasureInteger operation</span></span>

<span data-ttu-id="d570e-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d570e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d570e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d570e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d570e-105">Bir hisse kayıt içeriğini ölçer ve bir tamsayıya dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="d570e-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="d570e-106">Ölçüm standart hesaplama temeline göre yapılır, yani, ' nin eigenliğine göre yapılır `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="d570e-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="d570e-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="d570e-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="d570e-108">Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d570e-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d570e-109">Küçük endian kodlamasıyla bir hisse kayıt.</span><span class="sxs-lookup"><span data-stu-id="d570e-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="d570e-110">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d570e-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d570e-111">Ölçülen değerini içeren işaretsiz bir tamsayı `target` .</span><span class="sxs-lookup"><span data-stu-id="d570e-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d570e-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d570e-112">Remarks</span></span>

<span data-ttu-id="d570e-113">Bu işlem, giriş kaydını bir hedef makineye serbest bırakmak için uygun olan $ \ket{00\cnoktalara 0} $ durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="d570e-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="d570e-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d570e-114">See Also</span></span>

- [<span data-ttu-id="d570e-115">Microsoft. hisse. Canon. Measureıntegerin</span><span class="sxs-lookup"><span data-stu-id="d570e-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)