---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Applynicetumon Iertransform işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 6d3ad9ca2e0d10c264f8020e1f34687f6cbc9f94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218198"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="3aeca-102">Applynicetumon Iertransform işlemi</span><span class="sxs-lookup"><span data-stu-id="3aeca-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="3aeca-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3aeca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3aeca-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3aeca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3aeca-105">Küçük endian gösteriminde bir tamsayı içeren bir hisse kayıt üzerinde hisse Fourier dönüşümü gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="3aeca-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3aeca-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3aeca-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="3aeca-107">QS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3aeca-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3aeca-108">Hisse kayıt defteri</span><span class="sxs-lookup"><span data-stu-id="3aeca-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="3aeca-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3aeca-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3aeca-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3aeca-110">Remarks</span></span>

<span data-ttu-id="3aeca-111">Giriş ve çıkışın little endian kodlamada olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="3aeca-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="3aeca-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3aeca-112">See Also</span></span>

- [<span data-ttu-id="3aeca-113">Microsoft. hisse. Canon. Applynicetumoniertransformto</span><span class="sxs-lookup"><span data-stu-id="3aeca-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)