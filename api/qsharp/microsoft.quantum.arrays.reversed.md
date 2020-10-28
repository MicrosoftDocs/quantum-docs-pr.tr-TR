---
uid: Microsoft.Quantum.Arrays.Reversed
title: Ters çevrilmiş işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730042"
---
# <a name="reversed-function"></a><span data-ttu-id="d79e6-102">Ters çevrilmiş işlev</span><span class="sxs-lookup"><span data-stu-id="d79e6-102">Reversed function</span></span>

<span data-ttu-id="d79e6-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d79e6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d79e6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d79e6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d79e6-105">Giriş dizisi ile aynı öğeleri içeren, ancak ters sırada olan bir dizi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="d79e6-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d79e6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d79e6-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="d79e6-107">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="d79e6-107">array : 'T[]</span></span>

<span data-ttu-id="d79e6-108">Öğeleri ters sırada kopyalanacak olan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="d79e6-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="d79e6-109">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="d79e6-109">Output : 'T[]</span></span>

<span data-ttu-id="d79e6-110">Öğeleri içeren bir dizi `array[Length(array) - 1]` ..</span><span class="sxs-lookup"><span data-stu-id="d79e6-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="d79e6-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="d79e6-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d79e6-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="d79e6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d79e6-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="d79e6-113">'T</span></span>

<span data-ttu-id="d79e6-114">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="d79e6-114">The type of the array elements.</span></span>