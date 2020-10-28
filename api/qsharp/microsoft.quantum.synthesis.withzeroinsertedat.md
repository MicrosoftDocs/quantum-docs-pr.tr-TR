---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Withsıfırlaması ınsertedat işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 6e13251741dadb19740b208cdfc13a14964a48dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733879"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="b5fe9-102">Withsıfırlaması ınsertedat işlevi</span><span class="sxs-lookup"><span data-stu-id="b5fe9-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="b5fe9-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="b5fe9-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="b5fe9-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b5fe9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b5fe9-105">Tamsayıya 0 bit ekleyin</span><span class="sxs-lookup"><span data-stu-id="b5fe9-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="b5fe9-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b5fe9-106">Description</span></span>

<span data-ttu-id="b5fe9-107">Bu işlem bir tamsayı alır, bit olarak 0 ekler `position` ve güncelleştirilmiş değeri bir tamsayı olarak döndürür.</span><span class="sxs-lookup"><span data-stu-id="b5fe9-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="b5fe9-108">Örneğin, saat 2 ' de 2 ' ye (10 $ {10} $ = 1010_ {2} $) 0 eklemek 18 ($18 _ = {10} 10010_ $) sayısını döndürür {2} .</span><span class="sxs-lookup"><span data-stu-id="b5fe9-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="b5fe9-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="b5fe9-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="b5fe9-110">Konum: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5fe9-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5fe9-111">0 ' ın eklendiği konum</span><span class="sxs-lookup"><span data-stu-id="b5fe9-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="b5fe9-112">değer: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5fe9-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5fe9-113">Değiştirilen değer</span><span class="sxs-lookup"><span data-stu-id="b5fe9-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="b5fe9-114">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5fe9-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5fe9-115">Değiştirilen değer</span><span class="sxs-lookup"><span data-stu-id="b5fe9-115">Modified value</span></span>