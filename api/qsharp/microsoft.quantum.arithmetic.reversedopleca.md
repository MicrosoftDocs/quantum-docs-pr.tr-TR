---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: ReversedOpLECA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: b5413e43ad50ba7252705ef53b21e63650dbb2a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730514"
---
# <a name="reversedopleca-function"></a><span data-ttu-id="31a2a-102">ReversedOpLECA işlevi</span><span class="sxs-lookup"><span data-stu-id="31a2a-102">ReversedOpLECA function</span></span>

<span data-ttu-id="31a2a-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="31a2a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="31a2a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31a2a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31a2a-105">Küçük endian girişi alan bir işlem verildiğinde, büyük endian girişi alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="31a2a-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="31a2a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="31a2a-106">Input</span></span>

### <a name="op--littleendian--unit-adj--ctl"></a><span data-ttu-id="31a2a-107">Op: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama + CTL</span><span class="sxs-lookup"><span data-stu-id="31a2a-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="31a2a-108">Girişi geri çevrilme işlemi.</span><span class="sxs-lookup"><span data-stu-id="31a2a-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-adj--ctl"></a><span data-ttu-id="31a2a-109">Çıkış: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [bigenünlik birimi](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="31a2a-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="31a2a-110">Girişini büyük endian kaydı olarak kabul eden yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="31a2a-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="31a2a-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="31a2a-111">See Also</span></span>

- [<span data-ttu-id="31a2a-112">Microsoft. hisse. aritmetik. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="31a2a-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [<span data-ttu-id="31a2a-113">Microsoft. hisse. aritmetik. Smardoor</span><span class="sxs-lookup"><span data-stu-id="31a2a-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="31a2a-114">Microsoft. hisse. aritmetik. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="31a2a-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="31a2a-115">Microsoft. hisse. aritmetik. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="31a2a-115">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)