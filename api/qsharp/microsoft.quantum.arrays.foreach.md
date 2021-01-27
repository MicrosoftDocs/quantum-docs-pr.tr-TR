---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848595"
---
# <a name="foreach-operation"></a><span data-ttu-id="16189-102">ForEach işlemi</span><span class="sxs-lookup"><span data-stu-id="16189-102">ForEach operation</span></span>

<span data-ttu-id="16189-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="16189-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="16189-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16189-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16189-105">Dizi öğeleri için tanımlanan bir dizi ve bir işlem verildiğinde, işlem altındaki orijinal dizinin görüntülerinden oluşan yeni bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="16189-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="16189-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="16189-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="16189-107">eylem: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="16189-107">action : 'T => 'U</span></span> 

<span data-ttu-id="16189-108">`'T`Her öğesine öğesinden öğesine bir işlem `'U` uygulanır.</span><span class="sxs-lookup"><span data-stu-id="16189-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="16189-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="16189-109">array : 'T[]</span></span>

<span data-ttu-id="16189-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="16189-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="16189-111">Çıkış: ' U []</span><span class="sxs-lookup"><span data-stu-id="16189-111">Output : 'U[]</span></span>

<span data-ttu-id="16189-112">`'U[]`İşlem tarafından eşlenen öğelerin dizisi `action` .</span><span class="sxs-lookup"><span data-stu-id="16189-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="16189-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="16189-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="16189-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="16189-114">'T</span></span>

<span data-ttu-id="16189-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="16189-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="16189-116">' U</span><span class="sxs-lookup"><span data-stu-id="16189-116">'U</span></span>

<span data-ttu-id="16189-117">İşlemin sonuç türü `action` .</span><span class="sxs-lookup"><span data-stu-id="16189-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="16189-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="16189-118">Remarks</span></span>

<span data-ttu-id="16189-119">İşlem genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve bir işlem olduğunda `action : 'T -> 'U` dizinin öğelerini eşleyebilir ve yeni türde bir dizi üretebilir `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="16189-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>