---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Araya eklemeli işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848109"
---
# <a name="interleaved-function"></a><span data-ttu-id="d156c-102">Araya eklemeli işlev</span><span class="sxs-lookup"><span data-stu-id="d156c-102">Interleaved function</span></span>

<span data-ttu-id="d156c-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d156c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d156c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d156c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d156c-105">İki dizi (neredeyse) aynı boyutta bırakılır.</span><span class="sxs-lookup"><span data-stu-id="d156c-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="d156c-106">Description</span><span class="sxs-lookup"><span data-stu-id="d156c-106">Description</span></span>

<span data-ttu-id="d156c-107">Bu işlev, ilk dizideki ilk öğe, sonra ikinci dizideki ilk öğe ve benzeri gibi iki dizinin araya ekleme işlemi döndürür.</span><span class="sxs-lookup"><span data-stu-id="d156c-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="d156c-108">İlk dizi ikinciyle aynı uzunlukta olmalıdır ya da bir daha fazla öğeye sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="d156c-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="d156c-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="d156c-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="d156c-110">ilk: 'T []</span><span class="sxs-lookup"><span data-stu-id="d156c-110">first : 'T[]</span></span>

<span data-ttu-id="d156c-111">Araya eklemeli ilk dizi.</span><span class="sxs-lookup"><span data-stu-id="d156c-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="d156c-112">İkinci: 'T []</span><span class="sxs-lookup"><span data-stu-id="d156c-112">second : 'T[]</span></span>

<span data-ttu-id="d156c-113">Araya eklemeli ikinci dizi.</span><span class="sxs-lookup"><span data-stu-id="d156c-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="d156c-114">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="d156c-114">Output : 'T[]</span></span>

<span data-ttu-id="d156c-115">Araya eklemeli dizi</span><span class="sxs-lookup"><span data-stu-id="d156c-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d156c-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="d156c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d156c-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="d156c-117">'T</span></span>

<span data-ttu-id="d156c-118">Ve öğelerinin her öğesinin türü `first` `second` .</span><span class="sxs-lookup"><span data-stu-id="d156c-118">The type of each element of `first` and `second`.</span></span>

## <a name="example"></a><span data-ttu-id="d156c-119">Örnek</span><span class="sxs-lookup"><span data-stu-id="d156c-119">Example</span></span>

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```