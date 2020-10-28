---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: eabeb8e068ef32cf6717efd6e818271a667b39b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730530"
---
# <a name="reversedoplea-function"></a><span data-ttu-id="761db-102">ReversedOpLEA işlevi</span><span class="sxs-lookup"><span data-stu-id="761db-102">ReversedOpLEA function</span></span>

<span data-ttu-id="761db-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="761db-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="761db-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="761db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="761db-105">Küçük endian girişi alan bir işlem verildiğinde, büyük endian girişi alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="761db-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="761db-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="761db-106">Input</span></span>

### <a name="op--littleendian--unit-adj"></a><span data-ttu-id="761db-107">Op: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama</span><span class="sxs-lookup"><span data-stu-id="761db-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="761db-108">Girişi geri çevrilme işlemi.</span><span class="sxs-lookup"><span data-stu-id="761db-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-adj"></a><span data-ttu-id="761db-109">Çıkış: [bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="761db-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="761db-110">Girişini büyük endian kaydı olarak kabul eden yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="761db-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="761db-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="761db-111">See Also</span></span>

- [<span data-ttu-id="761db-112">Microsoft. hisse. aritmetik. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="761db-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="761db-113">Microsoft. hisse. aritmetik. Smardoor</span><span class="sxs-lookup"><span data-stu-id="761db-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="761db-114">Microsoft. hisse. aritmetik. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="761db-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="761db-115">Microsoft. hisse. aritmetik. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="761db-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)