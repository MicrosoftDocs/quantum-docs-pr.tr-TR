---
uid: Microsoft.Quantum.Canon.QFT
title: QFT işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 8f1aa8c3680a068e500503ca25afa9a49e4ef5bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205554"
---
# <a name="qft-operation"></a><span data-ttu-id="078d3-102">QFT işlemi</span><span class="sxs-lookup"><span data-stu-id="078d3-102">QFT operation</span></span>

<span data-ttu-id="078d3-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="078d3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="078d3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="078d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="078d3-105">Büyük endian gösteriminde bir tamsayı içeren bir hisse kayıt üzerinde hisse Fourier dönüşümü gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="078d3-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="078d3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="078d3-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="078d3-107">QS: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="078d3-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="078d3-108">Hisse kayıt defteri</span><span class="sxs-lookup"><span data-stu-id="078d3-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="078d3-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="078d3-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="078d3-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="078d3-110">Remarks</span></span>

<span data-ttu-id="078d3-111">Giriş ve çıkışın big endian kodlamada olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="078d3-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="078d3-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="078d3-112">See Also</span></span>

- [<span data-ttu-id="078d3-113">Microsoft. hisse. Canon. Applynicetumoniertransformto</span><span class="sxs-lookup"><span data-stu-id="078d3-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)