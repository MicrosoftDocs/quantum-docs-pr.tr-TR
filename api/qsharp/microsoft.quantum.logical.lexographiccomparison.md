---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: f0b68974a0ea26907b58971e4fa4b1f06f5714d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726017"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="caf23-102">LexographicComparison işlevi</span><span class="sxs-lookup"><span data-stu-id="caf23-102">LexographicComparison function</span></span>

<span data-ttu-id="caf23-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="caf23-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="caf23-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="caf23-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="caf23-105">Bir karşılaştırma işlevi verildiğinde, sözcüografiksel olarak iki diziyi karşılaştıran yeni bir işlev döndürür.</span><span class="sxs-lookup"><span data-stu-id="caf23-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="caf23-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="caf23-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="caf23-107">elementComparison: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="caf23-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="caf23-108">İki öğeyi karşılaştıran ve `x` `y` ' `x` den küçük veya eşitse dönen bir işlev `y` .</span><span class="sxs-lookup"><span data-stu-id="caf23-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="caf23-109">Çıkış: ('T [], 'T [])-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="caf23-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="caf23-110">İki diziyi karşılaştıran ve `xs` `ys` `xs` sözcüograf sıralamasına göre veya ona eşit olduğunda döndüren bir işlev `ys` .</span><span class="sxs-lookup"><span data-stu-id="caf23-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="caf23-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="caf23-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="caf23-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="caf23-112">'T</span></span>

<span data-ttu-id="caf23-113">Karşılaştırılan dizilerin öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="caf23-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="caf23-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="caf23-114">Remarks</span></span>

<span data-ttu-id="caf23-115">İki dizi arasındaki lexographic karşılaştırması `xs` ve `ys` Aşağıdaki yordam tarafından tanımlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="caf23-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="caf23-116">İki öğe olduğunu `x` ve `y` `elementComparison(x, y)` `elementComparison(y, x)` her ikisi de true olduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="caf23-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="caf23-117">Her iki dizi de eşdeğer olmayan ilk öğe çifti kadar öğe öğesi ile karşılaştırılır.</span><span class="sxs-lookup"><span data-stu-id="caf23-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="caf23-118">İlk olarak öğesine göre oluşan öğesini içeren dizi, `elementComparison` ilk olarak lexografik sıralaması içinde gerçekleştik.</span><span class="sxs-lookup"><span data-stu-id="caf23-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="caf23-119">Herhangi bir kaçınması öğesi bulunmazsa ve bir dizi diğerinin daha uzunsa, daha kısa bir dizi ilk olarak ortaya çıkar.</span><span class="sxs-lookup"><span data-stu-id="caf23-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="caf23-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="caf23-120">See Also</span></span>

- [<span data-ttu-id="caf23-121">Microsoft. hisse. Arrays. sıralanmış</span><span class="sxs-lookup"><span data-stu-id="caf23-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)