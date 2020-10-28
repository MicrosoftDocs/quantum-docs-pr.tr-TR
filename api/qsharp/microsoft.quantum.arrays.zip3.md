---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: f4b1a769614ee9434b2141b8fcb91f34cd071bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729919"
---
# <a name="zip3-function"></a><span data-ttu-id="fa475-102">Zip3 işlevi</span><span class="sxs-lookup"><span data-stu-id="fa475-102">Zip3 function</span></span>

<span data-ttu-id="fa475-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fa475-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fa475-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fa475-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="fa475-105">Zip3 kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="fa475-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="fa475-106">Lütfen <xref:Microsoft.Quantum.Arrays.Zipped3> bunun yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="fa475-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="fa475-107">Üç dizi verildiğinde, her bir 3 tanımlama grubu her bir orijinal diziden bir öğe içerdiği için, yeni bir 3-tanımlama dizisi döndürür.</span><span class="sxs-lookup"><span data-stu-id="fa475-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="fa475-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="fa475-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="fa475-109">ilk: 1 []</span><span class="sxs-lookup"><span data-stu-id="fa475-109">first : 'T1[]</span></span>

<span data-ttu-id="fa475-110">Her kayıt düzeninin ilk öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="fa475-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="fa475-111">İkinci: 'T 2 []</span><span class="sxs-lookup"><span data-stu-id="fa475-111">second : 'T2[]</span></span>

<span data-ttu-id="fa475-112">Her bir kayıt düzeninin ikinci öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="fa475-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="fa475-113">Üçüncü: 'T []</span><span class="sxs-lookup"><span data-stu-id="fa475-113">third : 'T3[]</span></span>

<span data-ttu-id="fa475-114">Her kayıt düzeninin üçüncü öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="fa475-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="fa475-115">Çıkış: (1, 'T 2, 'T 3) []</span><span class="sxs-lookup"><span data-stu-id="fa475-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="fa475-116">Her biri için formun 3-tanımlama gruplarını içeren bir dizi `(first[idx], second[idx], third[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="fa475-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="fa475-117">Üç dizi eşit değilse, çıkış girişlerin daha kısa olduğu uzunlukta olur.</span><span class="sxs-lookup"><span data-stu-id="fa475-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fa475-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="fa475-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="fa475-119">1 'T</span><span class="sxs-lookup"><span data-stu-id="fa475-119">'T1</span></span>

<span data-ttu-id="fa475-120">İlk dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="fa475-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="fa475-121">2.</span><span class="sxs-lookup"><span data-stu-id="fa475-121">'T2</span></span>

<span data-ttu-id="fa475-122">İkinci dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="fa475-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="fa475-123">1 'T</span><span class="sxs-lookup"><span data-stu-id="fa475-123">'T3</span></span>

<span data-ttu-id="fa475-124">Üçüncü dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="fa475-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa475-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fa475-125">See Also</span></span>

- [<span data-ttu-id="fa475-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="fa475-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="fa475-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="fa475-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)