---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBE
title: ApplyReversedOpBE işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBE
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: a181cb16d6ae7684d49fe200d72bcbf5209018e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731778"
---
# <a name="applyreversedopbe-operation"></a><span data-ttu-id="7816d-102">ApplyReversedOpBE işlemi</span><span class="sxs-lookup"><span data-stu-id="7816d-102">ApplyReversedOpBE operation</span></span>

<span data-ttu-id="7816d-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7816d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7816d-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7816d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7816d-105">Bir yazmaç için büyük endian girişi alan, küçük endian biçimini kullanarak işaretsiz bir tamsayı olan bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="7816d-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="7816d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7816d-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="7816d-107">Op: [bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7816d-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7816d-108">Büyük endian kaydı üzerinde davranan işlem.</span><span class="sxs-lookup"><span data-stu-id="7816d-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="7816d-109">kaydol: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7816d-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7816d-110">Dönüştürülecek küçük endian kaydı.</span><span class="sxs-lookup"><span data-stu-id="7816d-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7816d-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7816d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7816d-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7816d-112">See Also</span></span>

- [<span data-ttu-id="7816d-113">Microsoft. hisse. aritmetik. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="7816d-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="7816d-114">Microsoft. hisse. aritmetik. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="7816d-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="7816d-115">Microsoft. hisse. aritmetik. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="7816d-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)