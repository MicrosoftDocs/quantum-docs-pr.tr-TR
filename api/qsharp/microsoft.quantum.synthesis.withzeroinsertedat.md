---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Withsıfırlaması ınsertedat işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855208"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="c6751-102">Withsıfırlaması ınsertedat işlevi</span><span class="sxs-lookup"><span data-stu-id="c6751-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="c6751-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="c6751-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="c6751-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6751-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6751-105">Tamsayıya 0 bit ekleyin</span><span class="sxs-lookup"><span data-stu-id="c6751-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="c6751-106">Description</span><span class="sxs-lookup"><span data-stu-id="c6751-106">Description</span></span>

<span data-ttu-id="c6751-107">Bu işlem bir tamsayı alır, bit olarak 0 ekler `position` ve güncelleştirilmiş değeri bir tamsayı olarak döndürür.</span><span class="sxs-lookup"><span data-stu-id="c6751-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="c6751-108">Örneğin, saat 2 ' de 2 ' ye (10 $ {10} $ = 1010_ {2} $) 0 eklemek 18 ($18 _ = {10} 10010_ $) sayısını döndürür {2} .</span><span class="sxs-lookup"><span data-stu-id="c6751-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="c6751-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="c6751-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="c6751-110">Konum: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6751-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6751-111">0 ' ın eklendiği konum</span><span class="sxs-lookup"><span data-stu-id="c6751-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="c6751-112">değer: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6751-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6751-113">Değiştirilen değer</span><span class="sxs-lookup"><span data-stu-id="c6751-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="c6751-114">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6751-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6751-115">Değiştirilen değer</span><span class="sxs-lookup"><span data-stu-id="c6751-115">Modified value</span></span>