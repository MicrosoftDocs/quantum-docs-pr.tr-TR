---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850919"
---
# <a name="unique-function"></a><span data-ttu-id="f7c17-102">Unique işlevi</span><span class="sxs-lookup"><span data-stu-id="f7c17-102">Unique function</span></span>

<span data-ttu-id="f7c17-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f7c17-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f7c17-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7c17-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7c17-105">Eşit bitişik öğeleri olmayan yeni bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="f7c17-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="f7c17-106">Description</span><span class="sxs-lookup"><span data-stu-id="f7c17-106">Description</span></span>

<span data-ttu-id="f7c17-107">Bir dizi öğe ve eşitlik sınaması için bir işlev verildiğinde, bu işlev, öğelerin göreli sırasının tutulduğu yeni bir dizi döndürür, ancak eşit olan tüm bitişik öğeler yalnızca tek bir öğeye filtrelenir.</span><span class="sxs-lookup"><span data-stu-id="f7c17-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="f7c17-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="f7c17-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="f7c17-109">eşittir: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f7c17-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f7c17-110">`a` `b` `equal(a, b)` Öğesi ise, eşit olarak kabul edilen iki öğeyi karşılaştıran bir işlev `true` .</span><span class="sxs-lookup"><span data-stu-id="f7c17-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="f7c17-111">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="f7c17-111">array : 'T[]</span></span>

<span data-ttu-id="f7c17-112">Benzersiz öğeler için filtrelenecek dizi.</span><span class="sxs-lookup"><span data-stu-id="f7c17-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="f7c17-113">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="f7c17-113">Output : 'T[]</span></span>

<span data-ttu-id="f7c17-114">Eşit bitişik öğe olmayan dizi.</span><span class="sxs-lookup"><span data-stu-id="f7c17-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f7c17-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f7c17-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7c17-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f7c17-116">'T</span></span>

<span data-ttu-id="f7c17-117">Her öğesinin türü `array` .</span><span class="sxs-lookup"><span data-stu-id="f7c17-117">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="f7c17-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="f7c17-118">Example</span></span>

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a><span data-ttu-id="f7c17-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f7c17-119">Remarks</span></span>

<span data-ttu-id="f7c17-120">Eşit olan, diğeri yanında olmayan birden çok öğe varsa, çıkış dizisinde birden çok oluşum olur.</span><span class="sxs-lookup"><span data-stu-id="f7c17-120">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="f7c17-121">`Sorted`Genel benzersiz öğeler içeren bir dizi almak için bu işlevi ile birlikte kullanın.</span><span class="sxs-lookup"><span data-stu-id="f7c17-121">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>