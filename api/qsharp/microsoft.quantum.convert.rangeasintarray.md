---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214016"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="aea28-102">RangeAsIntArray işlevi</span><span class="sxs-lookup"><span data-stu-id="aea28-102">RangeAsIntArray function</span></span>

<span data-ttu-id="aea28-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="aea28-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="aea28-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aea28-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aea28-105">`arr`Start tarafından numaralandırılan tamsayılar dizisini oluşturur. adım.. erer.</span><span class="sxs-lookup"><span data-stu-id="aea28-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="aea28-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="aea28-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="aea28-107">Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="aea28-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="aea28-108">Bir `Range` `start..step..end` diziye dönüştürülecek değerler.</span><span class="sxs-lookup"><span data-stu-id="aea28-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="aea28-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="aea28-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="aea28-110">Tarafından tekrarlandırılmış değerlere karşılık gelen yeni tamsayılar dizisi `range` .</span><span class="sxs-lookup"><span data-stu-id="aea28-110">A new array of integers corresponding to values iterated over by `range`.</span></span>