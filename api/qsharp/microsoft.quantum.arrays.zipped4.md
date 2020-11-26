---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4 işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d5ee10ac9776383e75bc16a5c003a8b1a65c5698
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219643"
---
# <a name="zipped4-function"></a><span data-ttu-id="ec91d-102">Zipped4 işlevi</span><span class="sxs-lookup"><span data-stu-id="ec91d-102">Zipped4 function</span></span>

<span data-ttu-id="ec91d-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ec91d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ec91d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec91d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec91d-105">Dört dizi verildiğinde, her 4 tanımlama grubu her bir orijinal diziden bir öğe içerdiği için, yeni bir 4-tanımlama dizisi dizisi döndürür.</span><span class="sxs-lookup"><span data-stu-id="ec91d-105">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="ec91d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ec91d-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="ec91d-107">ilk: 1 []</span><span class="sxs-lookup"><span data-stu-id="ec91d-107">first : 'T1[]</span></span>

<span data-ttu-id="ec91d-108">Her kayıt düzeninin ilk öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="ec91d-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="ec91d-109">İkinci: 'T 2 []</span><span class="sxs-lookup"><span data-stu-id="ec91d-109">second : 'T2[]</span></span>

<span data-ttu-id="ec91d-110">Her bir kayıt düzeninin ikinci öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="ec91d-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="ec91d-111">Üçüncü: 'T []</span><span class="sxs-lookup"><span data-stu-id="ec91d-111">third : 'T3[]</span></span>

<span data-ttu-id="ec91d-112">Her kayıt düzeninin üçüncü öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="ec91d-112">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="ec91d-113">Dördüncü: 'T 4 []</span><span class="sxs-lookup"><span data-stu-id="ec91d-113">fourth : 'T4[]</span></span>

<span data-ttu-id="ec91d-114">Her kayıt düzeninin dördüncü öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="ec91d-114">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="ec91d-115">Çıkış: (1, 'T 2, 't 3, 'T 4) []</span><span class="sxs-lookup"><span data-stu-id="ec91d-115">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="ec91d-116">Her biri için formun 4-tanımlama gruplarını içeren bir dizi `(first[idx], second[idx], third[idx], fourth[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="ec91d-116">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="ec91d-117">Dört dizi eşit değilse, çıkış girişlerin daha kısa olduğu uzunlukta olur.</span><span class="sxs-lookup"><span data-stu-id="ec91d-117">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ec91d-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ec91d-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="ec91d-119">1 'T</span><span class="sxs-lookup"><span data-stu-id="ec91d-119">'T1</span></span>

<span data-ttu-id="ec91d-120">İlk dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="ec91d-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="ec91d-121">2.</span><span class="sxs-lookup"><span data-stu-id="ec91d-121">'T2</span></span>

<span data-ttu-id="ec91d-122">İkinci dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="ec91d-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="ec91d-123">1 'T</span><span class="sxs-lookup"><span data-stu-id="ec91d-123">'T3</span></span>

<span data-ttu-id="ec91d-124">Üçüncü dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="ec91d-124">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="ec91d-125">4 'T</span><span class="sxs-lookup"><span data-stu-id="ec91d-125">'T4</span></span>

<span data-ttu-id="ec91d-126">Dördüncü dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="ec91d-126">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec91d-127">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ec91d-127">See Also</span></span>

- [<span data-ttu-id="ec91d-128">Microsoft.Quantum.Arrays.Zipuygulanmış</span><span class="sxs-lookup"><span data-stu-id="ec91d-128">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="ec91d-129">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="ec91d-129">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)