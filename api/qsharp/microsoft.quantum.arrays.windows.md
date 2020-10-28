---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729935"
---
# <a name="windows-function"></a><span data-ttu-id="e79b6-102">Windows işlevi</span><span class="sxs-lookup"><span data-stu-id="e79b6-102">Windows function</span></span>

<span data-ttu-id="e79b6-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e79b6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e79b6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e79b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e79b6-105">Tüm birbirini izleyen alt dizileri döndürür `size` .</span><span class="sxs-lookup"><span data-stu-id="e79b6-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="e79b6-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e79b6-106">Description</span></span>

<span data-ttu-id="e79b6-107">Bu işlev, tüm `n - size + 1` alt dizileri sırasıyla döndürür `size` , burada olduğu gibi `n` `arr` .</span><span class="sxs-lookup"><span data-stu-id="e79b6-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="e79b6-108">İlk alt diziler `arr[0..size - 1], arr[1..size], arr[2..size + 1]` son alt diziye kadar `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="e79b6-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="e79b6-109">`size <= 0`Veya ise `size > n` boş bir dizi döndürülür.</span><span class="sxs-lookup"><span data-stu-id="e79b6-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="e79b6-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="e79b6-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="e79b6-111">Boyut: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e79b6-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e79b6-112">Alt dizilerin uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="e79b6-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="e79b6-113">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="e79b6-113">array : 'T[]</span></span>

<span data-ttu-id="e79b6-114">Bir dizi öğe.</span><span class="sxs-lookup"><span data-stu-id="e79b6-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="e79b6-115">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="e79b6-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e79b6-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e79b6-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e79b6-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e79b6-117">'T</span></span>

<span data-ttu-id="e79b6-118">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="e79b6-118">The type of `array` elements.</span></span>