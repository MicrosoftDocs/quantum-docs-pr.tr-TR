---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: Smardoor işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 6ebc4e97cb6d515e99e85922d03ca246b56084ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730535"
---
# <a name="reversedople-function"></a><span data-ttu-id="1c500-102">Smardoor işlevi</span><span class="sxs-lookup"><span data-stu-id="1c500-102">ReversedOpLE function</span></span>

<span data-ttu-id="1c500-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1c500-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1c500-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c500-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1c500-105">Küçük endian girişi alan bir işlem verildiğinde, büyük endian girişi alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="1c500-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="1c500-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1c500-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="1c500-107">Op: [littliendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c500-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1c500-108">Girişi geri çevrilme işlemi.</span><span class="sxs-lookup"><span data-stu-id="1c500-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="1c500-109">Çıkış: [bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c500-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1c500-110">Girişini büyük endian kaydı olarak kabul eden yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="1c500-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c500-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1c500-111">See Also</span></span>

- [<span data-ttu-id="1c500-112">Microsoft. hisse. aritmetik. Applysmardoor</span><span class="sxs-lookup"><span data-stu-id="1c500-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="1c500-113">Microsoft. hisse. aritmetik. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="1c500-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="1c500-114">Microsoft. hisse. aritmetik. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="1c500-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="1c500-115">Microsoft. hisse. aritmetik. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="1c500-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)