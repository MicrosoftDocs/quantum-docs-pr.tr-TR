---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA
title: ApplyReversedOpLECA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLECA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 6e4edd30e33be1a8039b7fd6551470abee26ea27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731719"
---
# <a name="applyreversedopleca-operation"></a><span data-ttu-id="afeb3-102">ApplyReversedOpLECA işlemi</span><span class="sxs-lookup"><span data-stu-id="afeb3-102">ApplyReversedOpLECA operation</span></span>

<span data-ttu-id="afeb3-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="afeb3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="afeb3-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afeb3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afeb3-105">Büyük endian biçimini kullanarak işaretsiz bir tamsayıyı bir yazmaç kodlamasına az endian girişi alan bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="afeb3-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="afeb3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="afeb3-106">Input</span></span>

### <a name="op--littleendian--unit-ctl--adj"></a><span data-ttu-id="afeb3-107">Op: [littliendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL + sıfatı</span><span class="sxs-lookup"><span data-stu-id="afeb3-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="afeb3-108">Az endian kayıt üzerinde davranan işlem.</span><span class="sxs-lookup"><span data-stu-id="afeb3-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="afeb3-109">kaydol: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="afeb3-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="afeb3-110">Dönüştürülecek büyük endian kaydı.</span><span class="sxs-lookup"><span data-stu-id="afeb3-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="afeb3-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="afeb3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="afeb3-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="afeb3-112">See Also</span></span>

- [<span data-ttu-id="afeb3-113">Microsoft. hisse. aritmetik. Applysmardoor</span><span class="sxs-lookup"><span data-stu-id="afeb3-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="afeb3-114">Microsoft. hisse. aritmetik. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="afeb3-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="afeb3-115">Microsoft. hisse. aritmetik. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="afeb3-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)