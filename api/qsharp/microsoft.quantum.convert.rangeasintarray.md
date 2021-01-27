---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850093"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="10d7d-102">RangeAsIntArray işlevi</span><span class="sxs-lookup"><span data-stu-id="10d7d-102">RangeAsIntArray function</span></span>

<span data-ttu-id="10d7d-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="10d7d-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="10d7d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="10d7d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="10d7d-105">`arr`Start tarafından numaralandırılan tamsayılar dizisini oluşturur. adım.. erer.</span><span class="sxs-lookup"><span data-stu-id="10d7d-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="10d7d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="10d7d-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="10d7d-107">Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="10d7d-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="10d7d-108">Bir `Range` `start..step..end` diziye dönüştürülecek değerler.</span><span class="sxs-lookup"><span data-stu-id="10d7d-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="10d7d-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="10d7d-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="10d7d-110">Tarafından tekrarlandırılmış değerlere karşılık gelen yeni tamsayılar dizisi `range` .</span><span class="sxs-lookup"><span data-stu-id="10d7d-110">A new array of integers corresponding to values iterated over by `range`.</span></span>

## <a name="example"></a><span data-ttu-id="10d7d-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="10d7d-111">Example</span></span>

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```