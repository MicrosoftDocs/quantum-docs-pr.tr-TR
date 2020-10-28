---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 170f63e60e6c26dbdd33af02c6a3387a1b3dbc44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730570"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="be1da-102">ReversedOpBE işlevi</span><span class="sxs-lookup"><span data-stu-id="be1da-102">ReversedOpBE function</span></span>

<span data-ttu-id="be1da-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="be1da-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="be1da-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be1da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be1da-105">Büyük endian girişi alan bir işlem verildiğinde, küçük endian girişi alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="be1da-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="be1da-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="be1da-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="be1da-107">Op: [bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be1da-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="be1da-108">Girişi geri çevrilme işlemi.</span><span class="sxs-lookup"><span data-stu-id="be1da-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="be1da-109">Çıkış: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be1da-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="be1da-110">Girişini küçük endian kaydı olarak kabul eden yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="be1da-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="be1da-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="be1da-111">See Also</span></span>

- [<span data-ttu-id="be1da-112">Microsoft. hisse. aritmetik. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="be1da-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="be1da-113">Microsoft. hisse. aritmetik. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="be1da-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="be1da-114">Microsoft. hisse. aritmetik. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="be1da-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="be1da-115">Microsoft. hisse. aritmetik. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="be1da-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)