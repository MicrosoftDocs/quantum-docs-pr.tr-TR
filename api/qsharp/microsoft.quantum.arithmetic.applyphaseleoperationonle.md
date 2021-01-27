---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: ApplyPhaseLEOperationOnLE işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: d94fdb55e051e76dd518eff14b80d1a24516bf8a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843672"
---
# <a name="applyphaseleoperationonle-operation"></a><span data-ttu-id="47274-102">ApplyPhaseLEOperationOnLE işlemi</span><span class="sxs-lookup"><span data-stu-id="47274-102">ApplyPhaseLEOperationOnLE operation</span></span>

<span data-ttu-id="47274-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="47274-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="47274-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47274-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47274-105"><xref:microsoft.quantum.arithmetic.littleendian>Türünde bir hedef kayıt üzerinde giriş olarak kayıt alan bir işlem uygular <xref:microsoft.quantum.arithmetic.phaselittleendian> .</span><span class="sxs-lookup"><span data-stu-id="47274-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.</span></span>

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="47274-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="47274-106">Input</span></span>

### <a name="op--phaselittleendian--unit"></a><span data-ttu-id="47274-107">Op: [phaselittliendian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47274-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="47274-108">Uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="47274-108">The operation to be applied.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="47274-109">Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="47274-109">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="47274-110">İşlemin uygulandığı kayıt.</span><span class="sxs-lookup"><span data-stu-id="47274-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="47274-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47274-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="47274-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="47274-112">Remarks</span></span>

<span data-ttu-id="47274-113">Kayıt, kullanılarak öğesine dönüştürülür `PhaseLittleEndian` <xref:microsoft.quantum.canon.qftle> ve öğesinden sonra özgün gösterimine döndürülür `op` .</span><span class="sxs-lookup"><span data-stu-id="47274-113">The register is transformed to `PhaseLittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="47274-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="47274-114">See Also</span></span>

- [<span data-ttu-id="47274-115">Microsoft. hisse. Canon. Applyphaseleoperationontaa</span><span class="sxs-lookup"><span data-stu-id="47274-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="47274-116">Microsoft. hisse. Canon. Applyphaseleoperationontaa</span><span class="sxs-lookup"><span data-stu-id="47274-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="47274-117">Microsoft. hisse. Canon. Applyphaseleoperationontaca</span><span class="sxs-lookup"><span data-stu-id="47274-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)