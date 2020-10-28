---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA
title: ApplyReversedOpBECA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBECA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 1a11b85e4eca627246d7b9d3b4c10824296e9a77
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731751"
---
# <a name="applyreversedopbeca-operation"></a><span data-ttu-id="81666-102">ApplyReversedOpBECA işlemi</span><span class="sxs-lookup"><span data-stu-id="81666-102">ApplyReversedOpBECA operation</span></span>

<span data-ttu-id="81666-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="81666-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="81666-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81666-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81666-105">Bir yazmaç için büyük endian girişi alan, küçük endian biçimini kullanarak işaretsiz bir tamsayı olan bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="81666-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="81666-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="81666-106">Input</span></span>

### <a name="op--bigendian--unit-ctl--adj"></a><span data-ttu-id="81666-107">Op: [bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL + ayarlanabilir</span><span class="sxs-lookup"><span data-stu-id="81666-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="81666-108">Büyük endian kaydı üzerinde davranan işlem.</span><span class="sxs-lookup"><span data-stu-id="81666-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="81666-109">kaydol: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="81666-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="81666-110">Dönüştürülecek küçük endian kaydı.</span><span class="sxs-lookup"><span data-stu-id="81666-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81666-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81666-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="81666-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="81666-112">See Also</span></span>

- [<span data-ttu-id="81666-113">Microsoft. hisse. aritmetik. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="81666-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="81666-114">Microsoft. hisse. aritmetik. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="81666-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="81666-115">Microsoft. hisse. aritmetik. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="81666-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)