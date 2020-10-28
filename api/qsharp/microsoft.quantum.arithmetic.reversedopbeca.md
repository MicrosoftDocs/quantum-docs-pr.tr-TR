---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBECA
title: ReversedOpBECA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBECA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5617e191260903ac25effc8b922810932b7dc505
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730546"
---
# <a name="reversedopbeca-function"></a><span data-ttu-id="68c2e-102">ReversedOpBECA işlevi</span><span class="sxs-lookup"><span data-stu-id="68c2e-102">ReversedOpBECA function</span></span>

<span data-ttu-id="68c2e-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="68c2e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="68c2e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="68c2e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="68c2e-105">Büyük endian girişi alan bir işlem verildiğinde, küçük endian girişi alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="68c2e-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="68c2e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="68c2e-106">Input</span></span>

### <a name="op--bigendian--unit-adj--ctl"></a><span data-ttu-id="68c2e-107">Op: [bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="68c2e-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="68c2e-108">Girişi geri çevrilme işlemi.</span><span class="sxs-lookup"><span data-stu-id="68c2e-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="68c2e-109">Çıkış: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama + CTL</span><span class="sxs-lookup"><span data-stu-id="68c2e-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="68c2e-110">Girişini küçük endian kaydı olarak kabul eden yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="68c2e-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="68c2e-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="68c2e-111">See Also</span></span>

- [<span data-ttu-id="68c2e-112">Microsoft. hisse. aritmetik. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="68c2e-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
- [<span data-ttu-id="68c2e-113">Microsoft. hisse. aritmetik. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="68c2e-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="68c2e-114">Microsoft. hisse. aritmetik. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="68c2e-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="68c2e-115">Microsoft. hisse. aritmetik. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="68c2e-115">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)