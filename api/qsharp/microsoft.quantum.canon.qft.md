---
uid: Microsoft.Quantum.Canon.QFT
title: QFT işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: e5b40be6c86647205fe1c764b6b043272296a354
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728478"
---
# <a name="qft-operation"></a><span data-ttu-id="74c1a-102">QFT işlemi</span><span class="sxs-lookup"><span data-stu-id="74c1a-102">QFT operation</span></span>

<span data-ttu-id="74c1a-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="74c1a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="74c1a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="74c1a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="74c1a-105">Büyük endian gösteriminde bir tamsayı içeren bir hisse kayıt üzerinde hisse Fourier dönüşümü gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="74c1a-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="74c1a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="74c1a-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="74c1a-107">QS: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="74c1a-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="74c1a-108">Hisse kayıt defteri</span><span class="sxs-lookup"><span data-stu-id="74c1a-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="74c1a-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74c1a-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="74c1a-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="74c1a-110">Remarks</span></span>

<span data-ttu-id="74c1a-111">Giriş ve çıkışın big endian kodlamada olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="74c1a-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="74c1a-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="74c1a-112">See Also</span></span>

- [<span data-ttu-id="74c1a-113">Microsoft. hisse. Canon. Applynicetumoniertransformto</span><span class="sxs-lookup"><span data-stu-id="74c1a-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)