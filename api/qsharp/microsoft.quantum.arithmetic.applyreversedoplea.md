---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA
title: ApplyReversedOpLEA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 073ba908f2a06d36a8b73237f6a12d974b9d4d15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731738"
---
# <a name="applyreversedoplea-operation"></a><span data-ttu-id="a3284-102">ApplyReversedOpLEA işlemi</span><span class="sxs-lookup"><span data-stu-id="a3284-102">ApplyReversedOpLEA operation</span></span>

<span data-ttu-id="a3284-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a3284-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a3284-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3284-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3284-105">Büyük endian biçimini kullanarak işaretsiz bir tamsayıyı bir yazmaç kodlamasına az endian girişi alan bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="a3284-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="a3284-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a3284-106">Input</span></span>

### <a name="op--littleendian--unit-adj"></a><span data-ttu-id="a3284-107">Op: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama</span><span class="sxs-lookup"><span data-stu-id="a3284-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a3284-108">Az endian kayıt üzerinde davranan işlem.</span><span class="sxs-lookup"><span data-stu-id="a3284-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="a3284-109">kaydol: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="a3284-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="a3284-110">Dönüştürülecek büyük endian kaydı.</span><span class="sxs-lookup"><span data-stu-id="a3284-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a3284-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3284-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a3284-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a3284-112">See Also</span></span>

- [<span data-ttu-id="a3284-113">Microsoft. hisse. aritmetik. Applysmardoor</span><span class="sxs-lookup"><span data-stu-id="a3284-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="a3284-114">Microsoft. hisse. aritmetik. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="a3284-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="a3284-115">Microsoft. hisse. aritmetik. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="a3284-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)