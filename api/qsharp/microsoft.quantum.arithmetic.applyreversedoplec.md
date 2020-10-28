---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: ApplyReversedOpLEC işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: ac9a6000140445a457a9abc46d5143dcb089883e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731735"
---
# <a name="applyreversedoplec-operation"></a><span data-ttu-id="b524e-102">ApplyReversedOpLEC işlemi</span><span class="sxs-lookup"><span data-stu-id="b524e-102">ApplyReversedOpLEC operation</span></span>

<span data-ttu-id="b524e-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b524e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b524e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b524e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b524e-105">Büyük endian biçimini kullanarak işaretsiz bir tamsayıyı bir yazmaç kodlamasına az endian girişi alan bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="b524e-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="b524e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b524e-106">Input</span></span>

### <a name="op--littleendian--unit-ctl"></a><span data-ttu-id="b524e-107">Op: [littliendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="b524e-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="b524e-108">Az endian kayıt üzerinde davranan işlem.</span><span class="sxs-lookup"><span data-stu-id="b524e-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="b524e-109">kaydol: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="b524e-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="b524e-110">Dönüştürülecek büyük endian kaydı.</span><span class="sxs-lookup"><span data-stu-id="b524e-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b524e-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b524e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b524e-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b524e-112">See Also</span></span>

- [<span data-ttu-id="b524e-113">Microsoft. hisse. aritmetik. Applysmardoor</span><span class="sxs-lookup"><span data-stu-id="b524e-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="b524e-114">Microsoft. hisse. aritmetik. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="b524e-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="b524e-115">Microsoft. hisse. aritmetik. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="b524e-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)