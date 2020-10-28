---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730239"
---
# <a name="foreach-operation"></a><span data-ttu-id="dbd73-102">ForEach işlemi</span><span class="sxs-lookup"><span data-stu-id="dbd73-102">ForEach operation</span></span>

<span data-ttu-id="dbd73-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dbd73-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dbd73-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dbd73-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dbd73-105">Dizi öğeleri için tanımlanan bir dizi ve bir işlem verildiğinde, işlem altındaki orijinal dizinin görüntülerinden oluşan yeni bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="dbd73-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="dbd73-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="dbd73-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="dbd73-107">eylem: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="dbd73-107">action : 'T => 'U</span></span> 

<span data-ttu-id="dbd73-108">`'T`Her öğesine öğesinden öğesine bir işlem `'U` uygulanır.</span><span class="sxs-lookup"><span data-stu-id="dbd73-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="dbd73-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="dbd73-109">array : 'T[]</span></span>

<span data-ttu-id="dbd73-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="dbd73-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="dbd73-111">Çıkış: ' U []</span><span class="sxs-lookup"><span data-stu-id="dbd73-111">Output : 'U[]</span></span>

<span data-ttu-id="dbd73-112">`'U[]`İşlem tarafından eşlenen öğelerin dizisi `action` .</span><span class="sxs-lookup"><span data-stu-id="dbd73-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dbd73-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="dbd73-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dbd73-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="dbd73-114">'T</span></span>

<span data-ttu-id="dbd73-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="dbd73-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="dbd73-116">' U</span><span class="sxs-lookup"><span data-stu-id="dbd73-116">'U</span></span>

<span data-ttu-id="dbd73-117">İşlemin sonuç türü `action` .</span><span class="sxs-lookup"><span data-stu-id="dbd73-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbd73-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="dbd73-118">Remarks</span></span>

<span data-ttu-id="dbd73-119">İşlem genel türler için tanımlanmıştır, yani bir dizi `'T[]` ve bir işlem olduğunda `action : 'T -> 'U` dizinin öğelerini eşleyebilir ve yeni türde bir dizi üretebilir `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="dbd73-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>