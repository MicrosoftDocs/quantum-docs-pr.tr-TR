---
uid: Microsoft.Quantum.Arrays.Subarray
title: Subarray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: ccc041da0213d1f5dc5c8b4ff7a03b8b01ad107d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845428"
---
# <a name="subarray-function"></a><span data-ttu-id="de4d2-102">Subarray işlevi</span><span class="sxs-lookup"><span data-stu-id="de4d2-102">Subarray function</span></span>

<span data-ttu-id="de4d2-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="de4d2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="de4d2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="de4d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="de4d2-105">Bir diziyi ve konumların bir listesini alır ve özgün dizinin öğelerinden belirtilen konumlara göre oluşturulmuş yeni bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="de4d2-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="de4d2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="de4d2-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="de4d2-107">dizinler: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="de4d2-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="de4d2-108">Alt diziyi tanımlamak için kullanılan tamsayıların listesi.</span><span class="sxs-lookup"><span data-stu-id="de4d2-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="de4d2-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="de4d2-109">array : 'T[]</span></span>

<span data-ttu-id="de4d2-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="de4d2-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="de4d2-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="de4d2-111">Output : 'T[]</span></span>

<span data-ttu-id="de4d2-112">`out`Dizinleri alt diziye karşılık gelen bir öğe dizisi, örneğin `out[idx] == array[indices[idx]]` .</span><span class="sxs-lookup"><span data-stu-id="de4d2-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="de4d2-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="de4d2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="de4d2-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="de4d2-114">'T</span></span>

<span data-ttu-id="de4d2-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="de4d2-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="de4d2-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="de4d2-116">Remarks</span></span>

<span data-ttu-id="de4d2-117">İşlevi genel türler için tanımlanır, yani bir dizi `'T[]` ve `Int[]` alt diziyi tanımlayan konumların bir listesi.</span><span class="sxs-lookup"><span data-stu-id="de4d2-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="de4d2-118">Alt dizinin oluşturulması, başvuruları korumanın aksine, belirtilen dizinin yeni ve derin bir kopyasını oluşturmaya göre belirlenir.</span><span class="sxs-lookup"><span data-stu-id="de4d2-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="de4d2-119">Eğer `Length(indices) < Length(array)` , bu işlev öğesinin bir alt kümesini döndürür `array` .</span><span class="sxs-lookup"><span data-stu-id="de4d2-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="de4d2-120">Diğer taraftan, `indices` yinelenen öğeler içeriyorsa, karşılık gelen öğeleri de `array` aynı şekilde yinelenir.</span><span class="sxs-lookup"><span data-stu-id="de4d2-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="de4d2-121">`indices`Ve `array` aynı uzunluysa, bu işlev permütasyon sağlar `array` .</span><span class="sxs-lookup"><span data-stu-id="de4d2-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>