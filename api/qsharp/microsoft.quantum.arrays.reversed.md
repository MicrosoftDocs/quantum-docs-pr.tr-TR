---
uid: Microsoft.Quantum.Arrays.Reversed
title: Ters çevrilmiş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845468"
---
# <a name="reversed-function"></a><span data-ttu-id="bb318-102">Ters çevrilmiş işlev</span><span class="sxs-lookup"><span data-stu-id="bb318-102">Reversed function</span></span>

<span data-ttu-id="bb318-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bb318-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bb318-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bb318-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bb318-105">Giriş dizisi ile aynı öğeleri içeren, ancak ters sırada olan bir dizi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="bb318-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="bb318-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="bb318-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="bb318-107">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="bb318-107">array : 'T[]</span></span>

<span data-ttu-id="bb318-108">Öğeleri ters sırada kopyalanacak olan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="bb318-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="bb318-109">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="bb318-109">Output : 'T[]</span></span>

<span data-ttu-id="bb318-110">Öğeleri içeren bir dizi `array[Length(array) - 1]` ..</span><span class="sxs-lookup"><span data-stu-id="bb318-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="bb318-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="bb318-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bb318-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="bb318-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bb318-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="bb318-113">'T</span></span>

<span data-ttu-id="bb318-114">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="bb318-114">The type of the array elements.</span></span>