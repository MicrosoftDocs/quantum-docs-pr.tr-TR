---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5e9aa6e6dfef74bca004170cf2b1cd91aa13f0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730554"
---
# <a name="reversedopbec-function"></a><span data-ttu-id="a2b70-102">ReversedOpBEC işlevi</span><span class="sxs-lookup"><span data-stu-id="a2b70-102">ReversedOpBEC function</span></span>

<span data-ttu-id="a2b70-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a2b70-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a2b70-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2b70-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a2b70-105">Büyük endian girişi alan bir işlem verildiğinde, küçük endian girişi alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="a2b70-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="a2b70-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a2b70-106">Input</span></span>

### <a name="op--bigendian--unit-ctl"></a><span data-ttu-id="a2b70-107">Op: [bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="a2b70-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="a2b70-108">Girişi geri çevrilme işlemi.</span><span class="sxs-lookup"><span data-stu-id="a2b70-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-ctl"></a><span data-ttu-id="a2b70-109">Çıkış: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="a2b70-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="a2b70-110">Girişini küçük endian kaydı olarak kabul eden yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="a2b70-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2b70-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a2b70-111">See Also</span></span>

- [<span data-ttu-id="a2b70-112">Microsoft. hisse. aritmetik. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="a2b70-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="a2b70-113">Microsoft. hisse. aritmetik. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="a2b70-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="a2b70-114">Microsoft. hisse. aritmetik. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="a2b70-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="a2b70-115">Microsoft. hisse. aritmetik. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="a2b70-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)