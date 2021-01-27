---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 893366833e5bd6b358884c11f4534609efd72d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852270"
---
# <a name="qftle-operation"></a><span data-ttu-id="68ebe-102">QFTLE işlemi</span><span class="sxs-lookup"><span data-stu-id="68ebe-102">QFTLE operation</span></span>

<span data-ttu-id="68ebe-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="68ebe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="68ebe-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68ebe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68ebe-105">Küçük endian gösteriminde bir tamsayı içeren bir hisse kayıt üzerinde hisse Fourier dönüşümü gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="68ebe-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="68ebe-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="68ebe-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="68ebe-107">QS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="68ebe-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="68ebe-108">Hisse kayıt defteri</span><span class="sxs-lookup"><span data-stu-id="68ebe-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="68ebe-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="68ebe-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="68ebe-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="68ebe-110">Remarks</span></span>

<span data-ttu-id="68ebe-111">Giriş ve çıkışın little endian kodlamada olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="68ebe-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="68ebe-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="68ebe-112">See Also</span></span>

- [<span data-ttu-id="68ebe-113">Microsoft. hisse. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="68ebe-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)