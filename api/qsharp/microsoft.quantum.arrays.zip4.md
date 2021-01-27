---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: 534721e6544a31f6f5d27db0c077e9d8c574aecd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850877"
---
# <a name="zip4-function"></a><span data-ttu-id="1d661-102">Zip4 işlevi</span><span class="sxs-lookup"><span data-stu-id="1d661-102">Zip4 function</span></span>

<span data-ttu-id="1d661-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1d661-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1d661-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1d661-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="1d661-105">Zip4 kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="1d661-105">Zip4 has been deprecated.</span></span> <span data-ttu-id="1d661-106">Lütfen <xref:Microsoft.Quantum.Arrays.Zipped4> bunun yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="1d661-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.</span></span>

<span data-ttu-id="1d661-107">Dört dizi verildiğinde, her 4 tanımlama grubu her bir orijinal diziden bir öğe içerdiği için, yeni bir 4-tanımlama dizisi dizisi döndürür.</span><span class="sxs-lookup"><span data-stu-id="1d661-107">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="1d661-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="1d661-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="1d661-109">ilk: 1 []</span><span class="sxs-lookup"><span data-stu-id="1d661-109">first : 'T1[]</span></span>

<span data-ttu-id="1d661-110">Her kayıt düzeninin ilk öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="1d661-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="1d661-111">İkinci: 'T 2 []</span><span class="sxs-lookup"><span data-stu-id="1d661-111">second : 'T2[]</span></span>

<span data-ttu-id="1d661-112">Her bir kayıt düzeninin ikinci öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="1d661-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="1d661-113">Üçüncü: 'T []</span><span class="sxs-lookup"><span data-stu-id="1d661-113">third : 'T3[]</span></span>

<span data-ttu-id="1d661-114">Her kayıt düzeninin üçüncü öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="1d661-114">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="1d661-115">Dördüncü: 'T 4 []</span><span class="sxs-lookup"><span data-stu-id="1d661-115">fourth : 'T4[]</span></span>

<span data-ttu-id="1d661-116">Her kayıt düzeninin dördüncü öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="1d661-116">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="1d661-117">Çıkış: (1, 'T 2, 't 3, 'T 4) []</span><span class="sxs-lookup"><span data-stu-id="1d661-117">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="1d661-118">Her biri için formun 4-tanımlama gruplarını içeren bir dizi `(first[idx], second[idx], third[idx], fourth[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="1d661-118">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="1d661-119">Dört dizi eşit değilse, çıkış girişlerin daha kısa olduğu uzunlukta olur.</span><span class="sxs-lookup"><span data-stu-id="1d661-119">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1d661-120">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="1d661-120">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="1d661-121">1 'T</span><span class="sxs-lookup"><span data-stu-id="1d661-121">'T1</span></span>

<span data-ttu-id="1d661-122">İlk dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="1d661-122">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="1d661-123">2.</span><span class="sxs-lookup"><span data-stu-id="1d661-123">'T2</span></span>

<span data-ttu-id="1d661-124">İkinci dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="1d661-124">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="1d661-125">1 'T</span><span class="sxs-lookup"><span data-stu-id="1d661-125">'T3</span></span>

<span data-ttu-id="1d661-126">Üçüncü dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="1d661-126">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="1d661-127">4 'T</span><span class="sxs-lookup"><span data-stu-id="1d661-127">'T4</span></span>

<span data-ttu-id="1d661-128">Dördüncü dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="1d661-128">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d661-129">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1d661-129">See Also</span></span>

- [<span data-ttu-id="1d661-130">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="1d661-130">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="1d661-131">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="1d661-131">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)