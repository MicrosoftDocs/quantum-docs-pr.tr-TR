---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Applydönemtumoniertransformin işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: a1f4a0a5e94465fc8bf3af344e2e19ee0d1d15e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841574"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="41f64-102">Applydönemtumoniertransformin işlemi</span><span class="sxs-lookup"><span data-stu-id="41f64-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="41f64-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="41f64-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="41f64-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41f64-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41f64-105">Büyük endian gösteriminde bir tamsayı içeren bir hisse kayıt üzerinde hisse Fourier dönüşümü gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="41f64-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="41f64-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="41f64-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="41f64-107">QS: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="41f64-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="41f64-108">Hisse kayıt defteri</span><span class="sxs-lookup"><span data-stu-id="41f64-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="41f64-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41f64-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="41f64-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="41f64-110">Remarks</span></span>

<span data-ttu-id="41f64-111">Giriş ve çıkışın big endian kodlamada olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="41f64-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="41f64-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="41f64-112">See Also</span></span>

- [<span data-ttu-id="41f64-113">Microsoft. hisse. Canon. yaklaşık Teqft</span><span class="sxs-lookup"><span data-stu-id="41f64-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="41f64-114">Microsoft. hisse. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="41f64-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)