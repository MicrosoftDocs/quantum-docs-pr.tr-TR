---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: ApplyReversedOpBEA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: f606011dd002d6eadc4f882005f4577aeb28cac0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731759"
---
# <a name="applyreversedopbea-operation"></a><span data-ttu-id="be5fb-102">ApplyReversedOpBEA işlemi</span><span class="sxs-lookup"><span data-stu-id="be5fb-102">ApplyReversedOpBEA operation</span></span>

<span data-ttu-id="be5fb-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="be5fb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="be5fb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be5fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be5fb-105">Bir yazmaç için büyük endian girişi alan, küçük endian biçimini kullanarak işaretsiz bir tamsayı olan bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="be5fb-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="be5fb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="be5fb-106">Input</span></span>

### <a name="op--bigendian--unit-adj"></a><span data-ttu-id="be5fb-107">Op: [bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="be5fb-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="be5fb-108">Büyük endian kaydı üzerinde davranan işlem.</span><span class="sxs-lookup"><span data-stu-id="be5fb-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="be5fb-109">kaydol: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="be5fb-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="be5fb-110">Dönüştürülecek küçük endian kaydı.</span><span class="sxs-lookup"><span data-stu-id="be5fb-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="be5fb-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be5fb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="be5fb-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="be5fb-112">See Also</span></span>

- [<span data-ttu-id="be5fb-113">Microsoft. hisse. aritmetik. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="be5fb-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="be5fb-114">Microsoft. hisse. aritmetik. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="be5fb-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="be5fb-115">Microsoft. hisse. aritmetik. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="be5fb-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)