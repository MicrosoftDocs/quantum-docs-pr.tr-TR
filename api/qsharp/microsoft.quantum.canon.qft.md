---
uid: Microsoft.Quantum.Canon.QFT
title: QFT işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 30f475c3850c248b5af58db1e4aac3638c4c0471
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852288"
---
# <a name="qft-operation"></a><span data-ttu-id="caa07-102">QFT işlemi</span><span class="sxs-lookup"><span data-stu-id="caa07-102">QFT operation</span></span>

<span data-ttu-id="caa07-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="caa07-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="caa07-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="caa07-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="caa07-105">Büyük endian gösteriminde bir tamsayı içeren bir hisse kayıt üzerinde hisse Fourier dönüşümü gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="caa07-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="caa07-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="caa07-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="caa07-107">QS: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="caa07-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="caa07-108">Hisse kayıt defteri</span><span class="sxs-lookup"><span data-stu-id="caa07-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="caa07-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="caa07-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="caa07-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="caa07-110">Remarks</span></span>

<span data-ttu-id="caa07-111">Giriş ve çıkışın big endian kodlamada olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="caa07-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="caa07-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="caa07-112">See Also</span></span>

- [<span data-ttu-id="caa07-113">Microsoft. hisse. Canon. Applynicetumoniertransformto</span><span class="sxs-lookup"><span data-stu-id="caa07-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)