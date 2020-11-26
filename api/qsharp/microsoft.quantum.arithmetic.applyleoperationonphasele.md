---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLE
title: ApplyLEOperationOnPhaseLE işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 33e6cb81916737bf5db467e10fd2aeebb619116a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190913"
---
# <a name="applyleoperationonphasele-operation"></a><span data-ttu-id="51cbf-102">ApplyLEOperationOnPhaseLE işlemi</span><span class="sxs-lookup"><span data-stu-id="51cbf-102">ApplyLEOperationOnPhaseLE operation</span></span>

<span data-ttu-id="51cbf-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="51cbf-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="51cbf-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="51cbf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="51cbf-105"><xref:microsoft.quantum.arithmetic.phaselittleendian>Türünde bir hedef kayıt üzerinde giriş olarak kayıt alan bir işlem uygular <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="51cbf-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="51cbf-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="51cbf-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="51cbf-107">Op: [littliendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51cbf-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="51cbf-108">Uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="51cbf-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="51cbf-109">Hedef: [Phaselitttaendian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="51cbf-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="51cbf-110">İşlemin uygulandığı kayıt.</span><span class="sxs-lookup"><span data-stu-id="51cbf-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="51cbf-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51cbf-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="51cbf-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="51cbf-112">Remarks</span></span>

<span data-ttu-id="51cbf-113">Kayıt, kullanılarak öğesine dönüştürülür `LittleEndian` <xref:microsoft.quantum.canon.qftle> ve öğesinden sonra özgün gösterimine döndürülür `op` .</span><span class="sxs-lookup"><span data-stu-id="51cbf-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="51cbf-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="51cbf-114">See Also</span></span>

- [<span data-ttu-id="51cbf-115">Microsoft. hisse. Canon. ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="51cbf-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="51cbf-116">Microsoft. hisse. Canon. ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="51cbf-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [<span data-ttu-id="51cbf-117">Microsoft. hisse. Canon. ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="51cbf-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)