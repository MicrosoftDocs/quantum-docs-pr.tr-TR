---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727499"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="25eac-102">RangeAsIntArray işlevi</span><span class="sxs-lookup"><span data-stu-id="25eac-102">RangeAsIntArray function</span></span>

<span data-ttu-id="25eac-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="25eac-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="25eac-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25eac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25eac-105">`arr`Start tarafından numaralandırılan tamsayılar dizisini oluşturur. adım.. erer.</span><span class="sxs-lookup"><span data-stu-id="25eac-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="25eac-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="25eac-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="25eac-107">Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="25eac-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="25eac-108">Bir `Range` `start..step..end` diziye dönüştürülecek değerler.</span><span class="sxs-lookup"><span data-stu-id="25eac-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="25eac-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="25eac-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="25eac-110">Tarafından tekrarlandırılmış değerlere karşılık gelen yeni tamsayılar dizisi `range` .</span><span class="sxs-lookup"><span data-stu-id="25eac-110">A new array of integers corresponding to values iterated over by `range`.</span></span>