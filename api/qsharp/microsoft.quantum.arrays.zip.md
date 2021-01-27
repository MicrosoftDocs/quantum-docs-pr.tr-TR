---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 8ed658003f749efd31b8d841cecbb0a23a471af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850893"
---
# <a name="zip-function"></a><span data-ttu-id="2cb96-102">Zip işlevi</span><span class="sxs-lookup"><span data-stu-id="2cb96-102">Zip function</span></span>

<span data-ttu-id="2cb96-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2cb96-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2cb96-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2cb96-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="2cb96-105">ZIP kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="2cb96-105">Zip has been deprecated.</span></span> <span data-ttu-id="2cb96-106">Lütfen <xref:Microsoft.Quantum.Arrays.Zipped> bunun yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="2cb96-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="2cb96-107">İki dizi verildiğinde, her bir çiftin her orijinal diziden bir öğe içermesi gibi yeni bir çift dizisi döndürür.</span><span class="sxs-lookup"><span data-stu-id="2cb96-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="2cb96-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="2cb96-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="2cb96-109">Sol: 'T []</span><span class="sxs-lookup"><span data-stu-id="2cb96-109">left : 'T[]</span></span>

<span data-ttu-id="2cb96-110">Her kayıt düzeninin ilk öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="2cb96-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="2cb96-111">Sağ: ' U []</span><span class="sxs-lookup"><span data-stu-id="2cb96-111">right : 'U[]</span></span>

<span data-ttu-id="2cb96-112">Her bir kayıt düzeninin ikinci öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="2cb96-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="2cb96-113">Çıkış: ('T, ' U) []</span><span class="sxs-lookup"><span data-stu-id="2cb96-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="2cb96-114">Her biri için form çiftlerini içeren bir dizi `(left[idx], right[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="2cb96-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="2cb96-115">İki dizi eşit değilse, çıkış girişlerin daha kısa olduğu uzunlukta olur.</span><span class="sxs-lookup"><span data-stu-id="2cb96-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2cb96-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2cb96-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2cb96-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="2cb96-117">'T</span></span>

<span data-ttu-id="2cb96-118">Sol dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="2cb96-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="2cb96-119">' U</span><span class="sxs-lookup"><span data-stu-id="2cb96-119">'U</span></span>

<span data-ttu-id="2cb96-120">Sağ dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="2cb96-120">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="2cb96-121">Örnek</span><span class="sxs-lookup"><span data-stu-id="2cb96-121">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zip(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="2cb96-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2cb96-122">See Also</span></span>

- [<span data-ttu-id="2cb96-123">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="2cb96-123">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="2cb96-124">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="2cb96-124">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="2cb96-125">Microsoft. hisse. Arrays. zip sıkıştırması</span><span class="sxs-lookup"><span data-stu-id="2cb96-125">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)