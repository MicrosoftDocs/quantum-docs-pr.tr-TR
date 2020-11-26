---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 8f32a23aa4379744b84c3b8d9c8f565e61c3c64e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219898"
---
# <a name="windows-function"></a><span data-ttu-id="b5b11-102">Windows işlevi</span><span class="sxs-lookup"><span data-stu-id="b5b11-102">Windows function</span></span>

<span data-ttu-id="b5b11-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b5b11-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b5b11-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5b11-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5b11-105">Tüm birbirini izleyen alt dizileri döndürür `size` .</span><span class="sxs-lookup"><span data-stu-id="b5b11-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="b5b11-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b5b11-106">Description</span></span>

<span data-ttu-id="b5b11-107">Bu işlev, tüm `n - size + 1` alt dizileri sırasıyla döndürür `size` , burada olduğu gibi `n` `arr` .</span><span class="sxs-lookup"><span data-stu-id="b5b11-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="b5b11-108">İlk alt diziler `arr[0..size - 1], arr[1..size], arr[2..size + 1]` son alt diziye kadar `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="b5b11-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="b5b11-109">`size <= 0`Veya ise `size > n` boş bir dizi döndürülür.</span><span class="sxs-lookup"><span data-stu-id="b5b11-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="b5b11-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="b5b11-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="b5b11-111">Boyut: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5b11-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5b11-112">Alt dizilerin uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="b5b11-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="b5b11-113">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="b5b11-113">array : 'T[]</span></span>

<span data-ttu-id="b5b11-114">Bir dizi öğe.</span><span class="sxs-lookup"><span data-stu-id="b5b11-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="b5b11-115">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="b5b11-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b5b11-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="b5b11-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b5b11-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="b5b11-117">'T</span></span>

<span data-ttu-id="b5b11-118">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="b5b11-118">The type of `array` elements.</span></span>