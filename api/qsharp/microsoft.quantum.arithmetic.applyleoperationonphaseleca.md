---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLECA
title: ApplyLEOperationOnPhaseLECA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLECA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 4762eb17b4c11e46b5b94498b7fc8fd2f855c659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190698"
---
# <a name="applyleoperationonphaseleca-operation"></a><span data-ttu-id="904f5-102">ApplyLEOperationOnPhaseLECA işlemi</span><span class="sxs-lookup"><span data-stu-id="904f5-102">ApplyLEOperationOnPhaseLECA operation</span></span>

<span data-ttu-id="904f5-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="904f5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="904f5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="904f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="904f5-105"><xref:microsoft.quantum.arithmetic.phaselittleendian>Türünde bir hedef kayıt üzerinde giriş olarak kayıt alan bir işlem uygular <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="904f5-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="904f5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="904f5-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="904f5-107">Op: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL</span><span class="sxs-lookup"><span data-stu-id="904f5-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="904f5-108">Uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="904f5-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="904f5-109">Hedef: [Phaselitttaendian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="904f5-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="904f5-110">İşlemin uygulandığı kayıt.</span><span class="sxs-lookup"><span data-stu-id="904f5-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="904f5-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="904f5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="904f5-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="904f5-112">Remarks</span></span>

<span data-ttu-id="904f5-113">Kayıt, kullanılarak öğesine dönüştürülür `LittleEndian` <xref:microsoft.quantum.canon.qftle> ve öğesinden sonra özgün gösterimine döndürülür `op` .</span><span class="sxs-lookup"><span data-stu-id="904f5-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="904f5-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="904f5-114">See Also</span></span>

- [<span data-ttu-id="904f5-115">Microsoft. hisse. Canon. ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="904f5-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="904f5-116">Microsoft. hisse. Canon. ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="904f5-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="904f5-117">Microsoft. hisse. Canon. ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="904f5-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)