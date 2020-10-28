---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC
title: ApplyReversedOpBEC işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEC
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 54c35ccea5e9c2d3ec7a3e6f325f78c3e602970e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731754"
---
# <a name="applyreversedopbec-operation"></a><span data-ttu-id="63c57-102">ApplyReversedOpBEC işlemi</span><span class="sxs-lookup"><span data-stu-id="63c57-102">ApplyReversedOpBEC operation</span></span>

<span data-ttu-id="63c57-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="63c57-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="63c57-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63c57-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63c57-105">Bir yazmaç için büyük endian girişi alan, küçük endian biçimini kullanarak işaretsiz bir tamsayı olan bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="63c57-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="63c57-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="63c57-106">Input</span></span>

### <a name="op--bigendian--unit-ctl"></a><span data-ttu-id="63c57-107">Op: [bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="63c57-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="63c57-108">Büyük endian kaydı üzerinde davranan işlem.</span><span class="sxs-lookup"><span data-stu-id="63c57-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="63c57-109">kaydol: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="63c57-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="63c57-110">Dönüştürülecek küçük endian kaydı.</span><span class="sxs-lookup"><span data-stu-id="63c57-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63c57-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63c57-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="63c57-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="63c57-112">See Also</span></span>

- [<span data-ttu-id="63c57-113">Microsoft. hisse. aritmetik. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="63c57-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="63c57-114">Microsoft. hisse. aritmetik. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="63c57-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="63c57-115">Microsoft. hisse. aritmetik. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="63c57-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)