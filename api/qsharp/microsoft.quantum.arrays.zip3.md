---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845365"
---
# <a name="zip3-function"></a><span data-ttu-id="543c6-102">Zip3 işlevi</span><span class="sxs-lookup"><span data-stu-id="543c6-102">Zip3 function</span></span>

<span data-ttu-id="543c6-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="543c6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="543c6-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="543c6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="543c6-105">Zip3 kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="543c6-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="543c6-106">Lütfen <xref:Microsoft.Quantum.Arrays.Zipped3> bunun yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="543c6-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="543c6-107">Üç dizi verildiğinde, her bir 3 tanımlama grubu her bir orijinal diziden bir öğe içerdiği için, yeni bir 3-tanımlama dizisi döndürür.</span><span class="sxs-lookup"><span data-stu-id="543c6-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="543c6-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="543c6-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="543c6-109">ilk: 1 []</span><span class="sxs-lookup"><span data-stu-id="543c6-109">first : 'T1[]</span></span>

<span data-ttu-id="543c6-110">Her kayıt düzeninin ilk öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="543c6-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="543c6-111">İkinci: 'T 2 []</span><span class="sxs-lookup"><span data-stu-id="543c6-111">second : 'T2[]</span></span>

<span data-ttu-id="543c6-112">Her bir kayıt düzeninin ikinci öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="543c6-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="543c6-113">Üçüncü: 'T []</span><span class="sxs-lookup"><span data-stu-id="543c6-113">third : 'T3[]</span></span>

<span data-ttu-id="543c6-114">Her kayıt düzeninin üçüncü öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="543c6-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="543c6-115">Çıkış: (1, 'T 2, 'T 3) []</span><span class="sxs-lookup"><span data-stu-id="543c6-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="543c6-116">Her biri için formun 3-tanımlama gruplarını içeren bir dizi `(first[idx], second[idx], third[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="543c6-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="543c6-117">Üç dizi eşit değilse, çıkış girişlerin daha kısa olduğu uzunlukta olur.</span><span class="sxs-lookup"><span data-stu-id="543c6-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="543c6-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="543c6-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="543c6-119">1 'T</span><span class="sxs-lookup"><span data-stu-id="543c6-119">'T1</span></span>

<span data-ttu-id="543c6-120">İlk dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="543c6-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="543c6-121">2.</span><span class="sxs-lookup"><span data-stu-id="543c6-121">'T2</span></span>

<span data-ttu-id="543c6-122">İkinci dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="543c6-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="543c6-123">1 'T</span><span class="sxs-lookup"><span data-stu-id="543c6-123">'T3</span></span>

<span data-ttu-id="543c6-124">Üçüncü dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="543c6-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="543c6-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="543c6-125">See Also</span></span>

- [<span data-ttu-id="543c6-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="543c6-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="543c6-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="543c6-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)