---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727440"
---
# <a name="rangereverse-function"></a><span data-ttu-id="31004-102">RangeReverse işlevi</span><span class="sxs-lookup"><span data-stu-id="31004-102">RangeReverse function</span></span>

<span data-ttu-id="31004-103">Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="31004-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="31004-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31004-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31004-105">Giriş aralığının tersine çevrilmiş yeni bir Aralık döndürür.</span><span class="sxs-lookup"><span data-stu-id="31004-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="31004-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="31004-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="31004-107">r: [Range](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="31004-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="31004-108">Giriş aralığı.</span><span class="sxs-lookup"><span data-stu-id="31004-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="31004-109">Çıkış: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="31004-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="31004-110">Verilen aralığın tersine çevrilmiş yeni bir Aralık.</span><span class="sxs-lookup"><span data-stu-id="31004-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="31004-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="31004-111">Remarks</span></span>

<span data-ttu-id="31004-112">Bir `end` `-step` `start` aralığın gerçek son öğesi ile aynı olamaz, bir aralığın ters çevrilmesinin yalnızca.... olduğunu `end` unutmayın.</span><span class="sxs-lookup"><span data-stu-id="31004-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>