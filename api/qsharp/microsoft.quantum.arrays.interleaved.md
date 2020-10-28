---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Araya eklemeli işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730199"
---
# <a name="interleaved-function"></a><span data-ttu-id="e66ba-102">Araya eklemeli işlev</span><span class="sxs-lookup"><span data-stu-id="e66ba-102">Interleaved function</span></span>

<span data-ttu-id="e66ba-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e66ba-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e66ba-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e66ba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e66ba-105">İki dizi (neredeyse) aynı boyutta bırakılır.</span><span class="sxs-lookup"><span data-stu-id="e66ba-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="e66ba-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e66ba-106">Description</span></span>

<span data-ttu-id="e66ba-107">Bu işlev, ilk dizideki ilk öğe, sonra ikinci dizideki ilk öğe ve benzeri gibi iki dizinin araya ekleme işlemi döndürür.</span><span class="sxs-lookup"><span data-stu-id="e66ba-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="e66ba-108">İlk dizi ikinciyle aynı uzunlukta olmalıdır ya da bir daha fazla öğeye sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="e66ba-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="e66ba-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="e66ba-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="e66ba-110">ilk: 'T []</span><span class="sxs-lookup"><span data-stu-id="e66ba-110">first : 'T[]</span></span>

<span data-ttu-id="e66ba-111">Araya eklemeli ilk dizi.</span><span class="sxs-lookup"><span data-stu-id="e66ba-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="e66ba-112">İkinci: 'T []</span><span class="sxs-lookup"><span data-stu-id="e66ba-112">second : 'T[]</span></span>

<span data-ttu-id="e66ba-113">Araya eklemeli ikinci dizi.</span><span class="sxs-lookup"><span data-stu-id="e66ba-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="e66ba-114">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="e66ba-114">Output : 'T[]</span></span>

<span data-ttu-id="e66ba-115">Araya eklemeli dizi</span><span class="sxs-lookup"><span data-stu-id="e66ba-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e66ba-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e66ba-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e66ba-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e66ba-117">'T</span></span>

<span data-ttu-id="e66ba-118">Ve öğelerinin her öğesinin türü `first` `second` .</span><span class="sxs-lookup"><span data-stu-id="e66ba-118">The type of each element of `first` and `second`.</span></span>