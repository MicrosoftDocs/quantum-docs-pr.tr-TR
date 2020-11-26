---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213846"
---
# <a name="rangereverse-function"></a><span data-ttu-id="7e4a1-102">RangeReverse işlevi</span><span class="sxs-lookup"><span data-stu-id="7e4a1-102">RangeReverse function</span></span>

<span data-ttu-id="7e4a1-103">Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="7e4a1-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="7e4a1-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7e4a1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7e4a1-105">Giriş aralığının tersine çevrilmiş yeni bir Aralık döndürür.</span><span class="sxs-lookup"><span data-stu-id="7e4a1-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="7e4a1-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7e4a1-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="7e4a1-107">r: [Range](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="7e4a1-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="7e4a1-108">Giriş aralığı.</span><span class="sxs-lookup"><span data-stu-id="7e4a1-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="7e4a1-109">Çıkış: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="7e4a1-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="7e4a1-110">Verilen aralığın tersine çevrilmiş yeni bir Aralık.</span><span class="sxs-lookup"><span data-stu-id="7e4a1-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e4a1-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7e4a1-111">Remarks</span></span>

<span data-ttu-id="7e4a1-112">Bir `end` `-step` `start` aralığın gerçek son öğesi ile aynı olamaz, bir aralığın ters çevrilmesinin yalnızca.... olduğunu `end` unutmayın.</span><span class="sxs-lookup"><span data-stu-id="7e4a1-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>