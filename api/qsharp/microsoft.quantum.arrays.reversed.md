---
uid: Microsoft.Quantum.Arrays.Reversed
title: Ters çevrilmiş işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 270f15c1d10b4397e258c750876095efc2b8e951
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220442"
---
# <a name="reversed-function"></a><span data-ttu-id="ebd1e-102">Ters çevrilmiş işlev</span><span class="sxs-lookup"><span data-stu-id="ebd1e-102">Reversed function</span></span>

<span data-ttu-id="ebd1e-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ebd1e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ebd1e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebd1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebd1e-105">Giriş dizisi ile aynı öğeleri içeren, ancak ters sırada olan bir dizi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="ebd1e-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ebd1e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ebd1e-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="ebd1e-107">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="ebd1e-107">array : 'T[]</span></span>

<span data-ttu-id="ebd1e-108">Öğeleri ters sırada kopyalanacak olan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="ebd1e-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="ebd1e-109">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="ebd1e-109">Output : 'T[]</span></span>

<span data-ttu-id="ebd1e-110">Öğeleri içeren bir dizi `array[Length(array) - 1]` ..</span><span class="sxs-lookup"><span data-stu-id="ebd1e-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="ebd1e-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="ebd1e-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ebd1e-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ebd1e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ebd1e-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ebd1e-113">'T</span></span>

<span data-ttu-id="ebd1e-114">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="ebd1e-114">The type of the array elements.</span></span>