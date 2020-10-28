---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: ApplyPhaseLEOperationOnLE işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: dacc52766cf72d2bd562b76fc4939f962133e9a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731802"
---
# <a name="applyphaseleoperationonle-operation"></a><span data-ttu-id="4fa37-102">ApplyPhaseLEOperationOnLE işlemi</span><span class="sxs-lookup"><span data-stu-id="4fa37-102">ApplyPhaseLEOperationOnLE operation</span></span>

<span data-ttu-id="4fa37-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4fa37-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4fa37-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4fa37-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4fa37-105"><xref:microsoft.quantum.arithmetic.littleendian>Türünde bir hedef kayıt üzerinde giriş olarak kayıt alan bir işlem uygular <xref:microsoft.quantum.arithmetic.phaselittleendian> .</span><span class="sxs-lookup"><span data-stu-id="4fa37-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.</span></span>

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="4fa37-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4fa37-106">Input</span></span>

### <a name="op--phaselittleendian--unit"></a><span data-ttu-id="4fa37-107">Op: [phaselittliendian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4fa37-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4fa37-108">Uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="4fa37-108">The operation to be applied.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="4fa37-109">Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4fa37-109">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4fa37-110">İşlemin uygulandığı kayıt.</span><span class="sxs-lookup"><span data-stu-id="4fa37-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4fa37-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4fa37-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4fa37-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4fa37-112">Remarks</span></span>

<span data-ttu-id="4fa37-113">Kayıt, kullanılarak öğesine dönüştürülür `PhaseLittleEndian` <xref:microsoft.quantum.canon.qftle> ve öğesinden sonra özgün gösterimine döndürülür `op` .</span><span class="sxs-lookup"><span data-stu-id="4fa37-113">The register is transformed to `PhaseLittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4fa37-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4fa37-114">See Also</span></span>

- [<span data-ttu-id="4fa37-115">Microsoft. hisse. Canon. Applyphaseleoperationontaa</span><span class="sxs-lookup"><span data-stu-id="4fa37-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="4fa37-116">Microsoft. hisse. Canon. Applyphaseleoperationontaa</span><span class="sxs-lookup"><span data-stu-id="4fa37-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="4fa37-117">Microsoft. hisse. Canon. Applyphaseleoperationontaca</span><span class="sxs-lookup"><span data-stu-id="4fa37-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)