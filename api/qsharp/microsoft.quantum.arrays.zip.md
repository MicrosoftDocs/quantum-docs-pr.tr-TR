---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 32fea60fc36bfdbaa2ab2f3560f291bf4ce4fa51
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729922"
---
# <a name="zip-function"></a><span data-ttu-id="469a7-102">Zip işlevi</span><span class="sxs-lookup"><span data-stu-id="469a7-102">Zip function</span></span>

<span data-ttu-id="469a7-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="469a7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="469a7-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="469a7-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="469a7-105">ZIP kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="469a7-105">Zip has been deprecated.</span></span> <span data-ttu-id="469a7-106">Lütfen <xref:Microsoft.Quantum.Arrays.Zipped> bunun yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="469a7-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="469a7-107">İki dizi verildiğinde, her bir çiftin her orijinal diziden bir öğe içermesi gibi yeni bir çift dizisi döndürür.</span><span class="sxs-lookup"><span data-stu-id="469a7-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="469a7-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="469a7-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="469a7-109">Sol: 'T []</span><span class="sxs-lookup"><span data-stu-id="469a7-109">left : 'T[]</span></span>

<span data-ttu-id="469a7-110">Her kayıt düzeninin ilk öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="469a7-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="469a7-111">Sağ: ' U []</span><span class="sxs-lookup"><span data-stu-id="469a7-111">right : 'U[]</span></span>

<span data-ttu-id="469a7-112">Her bir kayıt düzeninin ikinci öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="469a7-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="469a7-113">Çıkış: ('T, ' U) []</span><span class="sxs-lookup"><span data-stu-id="469a7-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="469a7-114">Her biri için form çiftlerini içeren bir dizi `(left[idx], right[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="469a7-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="469a7-115">İki dizi eşit değilse, çıkış girişlerin daha kısa olduğu uzunlukta olur.</span><span class="sxs-lookup"><span data-stu-id="469a7-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="469a7-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="469a7-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="469a7-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="469a7-117">'T</span></span>

<span data-ttu-id="469a7-118">Sol dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="469a7-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="469a7-119">' U</span><span class="sxs-lookup"><span data-stu-id="469a7-119">'U</span></span>

<span data-ttu-id="469a7-120">Sağ dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="469a7-120">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="469a7-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="469a7-121">See Also</span></span>

- [<span data-ttu-id="469a7-122">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="469a7-122">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="469a7-123">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="469a7-123">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="469a7-124">Microsoft. hisse. Arrays. zip sıkıştırması</span><span class="sxs-lookup"><span data-stu-id="469a7-124">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)