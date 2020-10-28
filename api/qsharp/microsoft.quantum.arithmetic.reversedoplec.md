---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: ReversedOpLEC işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 3a4872be6b81498c26ab9a14134940c5ef8628b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730527"
---
# <a name="reversedoplec-function"></a><span data-ttu-id="cdb1c-102">ReversedOpLEC işlevi</span><span class="sxs-lookup"><span data-stu-id="cdb1c-102">ReversedOpLEC function</span></span>

<span data-ttu-id="cdb1c-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cdb1c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cdb1c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cdb1c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cdb1c-105">Küçük endian girişi alan bir işlem verildiğinde, büyük endian girişi alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="cdb1c-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="cdb1c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="cdb1c-106">Input</span></span>

### <a name="op--littleendian--unit-ctl"></a><span data-ttu-id="cdb1c-107">Op: [littliendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="cdb1c-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="cdb1c-108">Girişi geri çevrilme işlemi.</span><span class="sxs-lookup"><span data-stu-id="cdb1c-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-ctl"></a><span data-ttu-id="cdb1c-109">Çıkış: [bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="cdb1c-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="cdb1c-110">Girişini büyük endian kaydı olarak kabul eden yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="cdb1c-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="cdb1c-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="cdb1c-111">See Also</span></span>

- [<span data-ttu-id="cdb1c-112">Microsoft. hisse. aritmetik. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="cdb1c-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="cdb1c-113">Microsoft. hisse. aritmetik. Smardoor</span><span class="sxs-lookup"><span data-stu-id="cdb1c-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="cdb1c-114">Microsoft. hisse. aritmetik. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="cdb1c-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="cdb1c-115">Microsoft. hisse. aritmetik. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="cdb1c-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)