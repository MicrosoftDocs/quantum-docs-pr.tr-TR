---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220017"
---
# <a name="unique-function"></a><span data-ttu-id="6f8a1-102">Unique işlevi</span><span class="sxs-lookup"><span data-stu-id="6f8a1-102">Unique function</span></span>

<span data-ttu-id="6f8a1-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6f8a1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6f8a1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f8a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f8a1-105">Eşit bitişik öğeleri olmayan yeni bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="6f8a1-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="6f8a1-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6f8a1-106">Description</span></span>

<span data-ttu-id="6f8a1-107">Bir dizi öğe ve eşitlik sınaması için bir işlev verildiğinde, bu işlev, öğelerin göreli sırasının tutulduğu yeni bir dizi döndürür, ancak eşit olan tüm bitişik öğeler yalnızca tek bir öğeye filtrelenir.</span><span class="sxs-lookup"><span data-stu-id="6f8a1-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="6f8a1-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="6f8a1-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="6f8a1-109">eşittir: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6f8a1-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6f8a1-110">`a` `b` `equal(a, b)` Öğesi ise, eşit olarak kabul edilen iki öğeyi karşılaştıran bir işlev `true` .</span><span class="sxs-lookup"><span data-stu-id="6f8a1-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="6f8a1-111">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="6f8a1-111">array : 'T[]</span></span>

<span data-ttu-id="6f8a1-112">Benzersiz öğeler için filtrelenecek dizi.</span><span class="sxs-lookup"><span data-stu-id="6f8a1-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="6f8a1-113">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="6f8a1-113">Output : 'T[]</span></span>

<span data-ttu-id="6f8a1-114">Eşit bitişik öğe olmayan dizi.</span><span class="sxs-lookup"><span data-stu-id="6f8a1-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6f8a1-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="6f8a1-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6f8a1-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="6f8a1-116">'T</span></span>

<span data-ttu-id="6f8a1-117">Her öğesinin türü `array` .</span><span class="sxs-lookup"><span data-stu-id="6f8a1-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f8a1-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6f8a1-118">Remarks</span></span>

<span data-ttu-id="6f8a1-119">Eşit olan, diğeri yanında olmayan birden çok öğe varsa, çıkış dizisinde birden çok oluşum olur.</span><span class="sxs-lookup"><span data-stu-id="6f8a1-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="6f8a1-120">`Sorted`Genel benzersiz öğeler içeren bir dizi almak için bu işlevi ile birlikte kullanın.</span><span class="sxs-lookup"><span data-stu-id="6f8a1-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>