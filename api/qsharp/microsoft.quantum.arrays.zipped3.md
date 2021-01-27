---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: 6a4ffaeff8e6248a708ab9f8f9a6ff0c2e9e08d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842185"
---
# <a name="zipped3-function"></a><span data-ttu-id="83824-102">Zipped3 işlevi</span><span class="sxs-lookup"><span data-stu-id="83824-102">Zipped3 function</span></span>

<span data-ttu-id="83824-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="83824-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="83824-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="83824-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="83824-105">Üç dizi verildiğinde, her bir 3 tanımlama grubu her bir orijinal diziden bir öğe içerdiği için, yeni bir 3-tanımlama dizisi döndürür.</span><span class="sxs-lookup"><span data-stu-id="83824-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="83824-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="83824-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="83824-107">ilk: 1 []</span><span class="sxs-lookup"><span data-stu-id="83824-107">first : 'T1[]</span></span>

<span data-ttu-id="83824-108">Her kayıt düzeninin ilk öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="83824-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="83824-109">İkinci: 'T 2 []</span><span class="sxs-lookup"><span data-stu-id="83824-109">second : 'T2[]</span></span>

<span data-ttu-id="83824-110">Her bir kayıt düzeninin ikinci öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="83824-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="83824-111">Üçüncü: 'T []</span><span class="sxs-lookup"><span data-stu-id="83824-111">third : 'T3[]</span></span>

<span data-ttu-id="83824-112">Her kayıt düzeninin üçüncü öğesi için değerler içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="83824-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="83824-113">Çıkış: (1, 'T 2, 'T 3) []</span><span class="sxs-lookup"><span data-stu-id="83824-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="83824-114">Her biri için formun 3-tanımlama gruplarını içeren bir dizi `(first[idx], second[idx], third[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="83824-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="83824-115">Üç dizi eşit değilse, çıkış girişlerin daha kısa olduğu uzunlukta olur.</span><span class="sxs-lookup"><span data-stu-id="83824-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="83824-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="83824-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="83824-117">1 'T</span><span class="sxs-lookup"><span data-stu-id="83824-117">'T1</span></span>

<span data-ttu-id="83824-118">İlk dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="83824-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="83824-119">2.</span><span class="sxs-lookup"><span data-stu-id="83824-119">'T2</span></span>

<span data-ttu-id="83824-120">İkinci dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="83824-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="83824-121">1 'T</span><span class="sxs-lookup"><span data-stu-id="83824-121">'T3</span></span>

<span data-ttu-id="83824-122">Üçüncü dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="83824-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="83824-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="83824-123">See Also</span></span>

- [<span data-ttu-id="83824-124">Microsoft.Quantum.Arrays.Zipuygulanmış</span><span class="sxs-lookup"><span data-stu-id="83824-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="83824-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="83824-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)