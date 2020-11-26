---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Araya eklemeli işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220969"
---
# <a name="interleaved-function"></a><span data-ttu-id="ba66d-102">Araya eklemeli işlev</span><span class="sxs-lookup"><span data-stu-id="ba66d-102">Interleaved function</span></span>

<span data-ttu-id="ba66d-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ba66d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ba66d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ba66d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ba66d-105">İki dizi (neredeyse) aynı boyutta bırakılır.</span><span class="sxs-lookup"><span data-stu-id="ba66d-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="ba66d-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ba66d-106">Description</span></span>

<span data-ttu-id="ba66d-107">Bu işlev, ilk dizideki ilk öğe, sonra ikinci dizideki ilk öğe ve benzeri gibi iki dizinin araya ekleme işlemi döndürür.</span><span class="sxs-lookup"><span data-stu-id="ba66d-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="ba66d-108">İlk dizi ikinciyle aynı uzunlukta olmalıdır ya da bir daha fazla öğeye sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="ba66d-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="ba66d-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="ba66d-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="ba66d-110">ilk: 'T []</span><span class="sxs-lookup"><span data-stu-id="ba66d-110">first : 'T[]</span></span>

<span data-ttu-id="ba66d-111">Araya eklemeli ilk dizi.</span><span class="sxs-lookup"><span data-stu-id="ba66d-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="ba66d-112">İkinci: 'T []</span><span class="sxs-lookup"><span data-stu-id="ba66d-112">second : 'T[]</span></span>

<span data-ttu-id="ba66d-113">Araya eklemeli ikinci dizi.</span><span class="sxs-lookup"><span data-stu-id="ba66d-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="ba66d-114">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="ba66d-114">Output : 'T[]</span></span>

<span data-ttu-id="ba66d-115">Araya eklemeli dizi</span><span class="sxs-lookup"><span data-stu-id="ba66d-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ba66d-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ba66d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ba66d-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ba66d-117">'T</span></span>

<span data-ttu-id="ba66d-118">Ve öğelerinin her öğesinin türü `first` `second` .</span><span class="sxs-lookup"><span data-stu-id="ba66d-118">The type of each element of `first` and `second`.</span></span>