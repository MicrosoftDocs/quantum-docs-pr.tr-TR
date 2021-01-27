---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: ReversedOpLECA işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d4245437f2b71abb8bf1bbe4db43ae7d2ee23799
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845744"
---
# <a name="reversedopleca-function"></a><span data-ttu-id="ad75c-102">ReversedOpLECA işlevi</span><span class="sxs-lookup"><span data-stu-id="ad75c-102">ReversedOpLECA function</span></span>

<span data-ttu-id="ad75c-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ad75c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ad75c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad75c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad75c-105">Küçük endian girişi alan bir işlem verildiğinde, büyük endian girişi alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="ad75c-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="ad75c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ad75c-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="ad75c-107">Op: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL</span><span class="sxs-lookup"><span data-stu-id="ad75c-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ad75c-108">Girişi geri çevrilme işlemi.</span><span class="sxs-lookup"><span data-stu-id="ad75c-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="ad75c-109">Çıkış: [bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL</span><span class="sxs-lookup"><span data-stu-id="ad75c-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ad75c-110">Girişini büyük endian kaydı olarak kabul eden yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="ad75c-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad75c-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ad75c-111">See Also</span></span>

- [<span data-ttu-id="ad75c-112">Microsoft. hisse. aritmetik. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="ad75c-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [<span data-ttu-id="ad75c-113">Microsoft. hisse. aritmetik. Smardoor</span><span class="sxs-lookup"><span data-stu-id="ad75c-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="ad75c-114">Microsoft. hisse. aritmetik. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="ad75c-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="ad75c-115">Microsoft. hisse. aritmetik. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="ad75c-115">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)