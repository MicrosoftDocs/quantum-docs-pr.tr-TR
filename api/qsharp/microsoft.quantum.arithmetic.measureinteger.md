---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Measureınteger işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: e3ff06e5cbb2ef8a63e4ad12308b382347c90fc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222652"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="08200-102">Measureınteger işlemi</span><span class="sxs-lookup"><span data-stu-id="08200-102">MeasureInteger operation</span></span>

<span data-ttu-id="08200-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="08200-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="08200-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="08200-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="08200-105">Bir hisse kayıt içeriğini ölçer ve bir tamsayıya dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="08200-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="08200-106">Ölçüm standart hesaplama temeline göre yapılır, yani, ' nin eigenliğine göre yapılır `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="08200-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="08200-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="08200-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="08200-108">Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="08200-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="08200-109">Küçük endian kodlamasıyla bir hisse kayıt.</span><span class="sxs-lookup"><span data-stu-id="08200-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="08200-110">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="08200-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="08200-111">Ölçülen değerini içeren işaretsiz bir tamsayı `target` .</span><span class="sxs-lookup"><span data-stu-id="08200-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="08200-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="08200-112">Remarks</span></span>

<span data-ttu-id="08200-113">Bu işlem, giriş kaydını bir hedef makineye serbest bırakmak için uygun olan $ \ket{00\cnoktalara 0} $ durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="08200-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="08200-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="08200-114">See Also</span></span>

- [<span data-ttu-id="08200-115">Microsoft. hisse. Canon. Measureıntegerin</span><span class="sxs-lookup"><span data-stu-id="08200-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)