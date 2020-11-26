---
uid: Microsoft.Quantum.Arrays.Zipped
title: Daraltılmış işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219762"
---
# <a name="zipped-function"></a><span data-ttu-id="e0713-102">Daraltılmış işlev</span><span class="sxs-lookup"><span data-stu-id="e0713-102">Zipped function</span></span>

<span data-ttu-id="e0713-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e0713-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e0713-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0713-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0713-105">İki dizi verildiğinde, her bir çiftin her orijinal diziden bir öğe içermesi gibi yeni bir çift dizisi döndürür.</span><span class="sxs-lookup"><span data-stu-id="e0713-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="e0713-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e0713-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="e0713-107">Sol: 'T []</span><span class="sxs-lookup"><span data-stu-id="e0713-107">left : 'T[]</span></span>

<span data-ttu-id="e0713-108">Her kayıt düzeninin ilk öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="e0713-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="e0713-109">Sağ: ' U []</span><span class="sxs-lookup"><span data-stu-id="e0713-109">right : 'U[]</span></span>

<span data-ttu-id="e0713-110">Her bir kayıt düzeninin ikinci öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="e0713-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="e0713-111">Çıkış: ('T, ' U) []</span><span class="sxs-lookup"><span data-stu-id="e0713-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="e0713-112">Her biri için form çiftlerini içeren bir dizi `(left[idx], right[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="e0713-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="e0713-113">İki dizi eşit değilse, çıkış girişlerin daha kısa olduğu uzunlukta olur.</span><span class="sxs-lookup"><span data-stu-id="e0713-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e0713-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e0713-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e0713-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e0713-115">'T</span></span>

<span data-ttu-id="e0713-116">Sol dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="e0713-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="e0713-117">' U</span><span class="sxs-lookup"><span data-stu-id="e0713-117">'U</span></span>

<span data-ttu-id="e0713-118">Sağ dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="e0713-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0713-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e0713-119">See Also</span></span>

- [<span data-ttu-id="e0713-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="e0713-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="e0713-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="e0713-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="e0713-122">Microsoft. hisse. Arrays. zip sıkıştırması</span><span class="sxs-lookup"><span data-stu-id="e0713-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)