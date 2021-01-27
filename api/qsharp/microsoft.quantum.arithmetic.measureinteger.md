---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Measureınteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843115"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="91c6e-102">Measureınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="91c6e-102">MeasureInteger operation</span></span>

<span data-ttu-id="91c6e-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="91c6e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="91c6e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91c6e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91c6e-105">Bir hisse kayıt içeriğini ölçer ve bir tamsayıya dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="91c6e-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="91c6e-106">Ölçüm standart hesaplama temeline göre yapılır, yani, ' nin eigenliğine göre yapılır `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="91c6e-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="91c6e-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="91c6e-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="91c6e-108">Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="91c6e-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="91c6e-109">Küçük endian kodlamasıyla bir hisse kayıt.</span><span class="sxs-lookup"><span data-stu-id="91c6e-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="91c6e-110">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91c6e-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91c6e-111">Ölçülen değerini içeren işaretsiz bir tamsayı `target` .</span><span class="sxs-lookup"><span data-stu-id="91c6e-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="91c6e-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="91c6e-112">Remarks</span></span>

<span data-ttu-id="91c6e-113">Bu işlem, giriş kaydını bir hedef makineye serbest bırakmak için uygun olan $ \ket{00\cnoktalara 0} $ durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="91c6e-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="91c6e-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="91c6e-114">See Also</span></span>

- [<span data-ttu-id="91c6e-115">Microsoft. hisse. Canon. Measureıntegerin</span><span class="sxs-lookup"><span data-stu-id="91c6e-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)