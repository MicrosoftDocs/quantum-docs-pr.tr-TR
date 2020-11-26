---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Applydönemtumoniertransformin işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 39db7b4c69f7f06418ec257c013837c65b9cc67a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209052"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="8c9c5-102">Applydönemtumoniertransformin işlemi</span><span class="sxs-lookup"><span data-stu-id="8c9c5-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="8c9c5-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8c9c5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8c9c5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8c9c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8c9c5-105">Büyük endian gösteriminde bir tamsayı içeren bir hisse kayıt üzerinde hisse Fourier dönüşümü gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8c9c5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8c9c5-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="8c9c5-107">QS: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="8c9c5-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="8c9c5-108">Hisse kayıt defteri</span><span class="sxs-lookup"><span data-stu-id="8c9c5-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="8c9c5-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8c9c5-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8c9c5-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8c9c5-110">Remarks</span></span>

<span data-ttu-id="8c9c5-111">Giriş ve çıkışın big endian kodlamada olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c9c5-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8c9c5-112">See Also</span></span>

- [<span data-ttu-id="8c9c5-113">Microsoft. hisse. Canon. yaklaşık Teqft</span><span class="sxs-lookup"><span data-stu-id="8c9c5-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="8c9c5-114">Microsoft. hisse. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="8c9c5-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)