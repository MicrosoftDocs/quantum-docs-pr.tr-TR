---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 5fac832ef5b7d7be2d85675a32f45e66312f66c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200381"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="04647-102">SteaneCodeRecoveryX işlevi</span><span class="sxs-lookup"><span data-stu-id="04647-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="04647-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="04647-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="04647-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04647-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04647-105">⟦ 7, 1, 3 ⟧ Steane hisse kodu için bir sabitleyici grubunun X bölümü için kod çözücü.</span><span class="sxs-lookup"><span data-stu-id="04647-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="04647-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="04647-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="04647-107">sendromu: [sendromu](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="04647-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="04647-108">Sabitleştirici X bölümünü ölçerek elde edilen bir Sendromu dizisi.</span><span class="sxs-lookup"><span data-stu-id="04647-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="04647-109">Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="04647-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="04647-110">Kodlanmış hisse sisteme uygulandığında öğesine karşılık gelen hatayı düzelten Pauli işlemleri dizisi `syndrome` .</span><span class="sxs-lookup"><span data-stu-id="04647-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="04647-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="04647-111">Remarks</span></span>

<span data-ttu-id="04647-112">Seçilen kod çözücüsü, ⟦ 7, 1, 3 ⟧ Steane kodunun CSS Code özelliğini kullanır, yani X hatalarını ve Z hatalarını ayrı olarak düzeltir.</span><span class="sxs-lookup"><span data-stu-id="04647-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="04647-113">Kodun bir özelliği, sırasıyla x, sırasıyla z özelliğinin, bir tamsayı kabul edildiğinde x, z sendromu 'nin 3 bitlik kodlamasıdır.</span><span class="sxs-lookup"><span data-stu-id="04647-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="04647-114">Başvurular</span><span class="sxs-lookup"><span data-stu-id="04647-114">References</span></span>

- <span data-ttu-id="04647-115">D.</span><span class="sxs-lookup"><span data-stu-id="04647-115">D.</span></span> <span data-ttu-id="04647-116">Gottesman, "sabitleyici kodlar ve hisse hata düzeltmesi," Ph.D. sıra, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="04647-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="04647-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="04647-117">See Also</span></span>

- [<span data-ttu-id="04647-118">Microsoft. hisse. Errordüzeltmesini. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="04647-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="04647-119">Microsoft. hisse. Errordüzeltmesini. SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="04647-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)