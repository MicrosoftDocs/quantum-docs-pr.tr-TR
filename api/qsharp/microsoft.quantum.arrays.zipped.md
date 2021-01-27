---
uid: Microsoft.Quantum.Arrays.Zipped
title: Daraltılmış işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845344"
---
# <a name="zipped-function"></a><span data-ttu-id="40e97-102">Daraltılmış işlev</span><span class="sxs-lookup"><span data-stu-id="40e97-102">Zipped function</span></span>

<span data-ttu-id="40e97-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="40e97-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="40e97-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="40e97-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="40e97-105">İki dizi verildiğinde, her bir çiftin her orijinal diziden bir öğe içermesi gibi yeni bir çift dizisi döndürür.</span><span class="sxs-lookup"><span data-stu-id="40e97-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="40e97-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="40e97-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="40e97-107">Sol: 'T []</span><span class="sxs-lookup"><span data-stu-id="40e97-107">left : 'T[]</span></span>

<span data-ttu-id="40e97-108">Her kayıt düzeninin ilk öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="40e97-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="40e97-109">Sağ: ' U []</span><span class="sxs-lookup"><span data-stu-id="40e97-109">right : 'U[]</span></span>

<span data-ttu-id="40e97-110">Her bir kayıt düzeninin ikinci öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="40e97-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="40e97-111">Çıkış: ('T, ' U) []</span><span class="sxs-lookup"><span data-stu-id="40e97-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="40e97-112">Her biri için form çiftlerini içeren bir dizi `(left[idx], right[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="40e97-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="40e97-113">İki dizi eşit değilse, çıkış girişlerin daha kısa olduğu uzunlukta olur.</span><span class="sxs-lookup"><span data-stu-id="40e97-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="40e97-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="40e97-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="40e97-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="40e97-115">'T</span></span>

<span data-ttu-id="40e97-116">Sol dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="40e97-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="40e97-117">' U</span><span class="sxs-lookup"><span data-stu-id="40e97-117">'U</span></span>

<span data-ttu-id="40e97-118">Sağ dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="40e97-118">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="40e97-119">Örnek</span><span class="sxs-lookup"><span data-stu-id="40e97-119">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="40e97-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="40e97-120">See Also</span></span>

- [<span data-ttu-id="40e97-121">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="40e97-121">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="40e97-122">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="40e97-122">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="40e97-123">Microsoft. hisse. Arrays. zip sıkıştırması</span><span class="sxs-lookup"><span data-stu-id="40e97-123">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)