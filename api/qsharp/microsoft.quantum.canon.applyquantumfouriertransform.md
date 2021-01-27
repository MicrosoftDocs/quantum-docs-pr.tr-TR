---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Applynicetumon Iertransform işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: d99000c21c79d2ca97b1fe92ad331c7ba8599700
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844768"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="3b019-102">Applynicetumon Iertransform işlemi</span><span class="sxs-lookup"><span data-stu-id="3b019-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="3b019-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3b019-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3b019-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3b019-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3b019-105">Küçük endian gösteriminde bir tamsayı içeren bir hisse kayıt üzerinde hisse Fourier dönüşümü gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="3b019-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3b019-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3b019-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="3b019-107">QS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3b019-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3b019-108">Hisse kayıt defteri</span><span class="sxs-lookup"><span data-stu-id="3b019-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="3b019-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3b019-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3b019-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3b019-110">Remarks</span></span>

<span data-ttu-id="3b019-111">Giriş ve çıkışın little endian kodlamada olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="3b019-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b019-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3b019-112">See Also</span></span>

- [<span data-ttu-id="3b019-113">Microsoft. hisse. Canon. Applynicetumoniertransformto</span><span class="sxs-lookup"><span data-stu-id="3b019-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)