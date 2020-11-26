---
uid: Microsoft.Quantum.Arrays.Where
title: WHERE işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219932"
---
# <a name="where-function"></a><span data-ttu-id="c896d-102">WHERE işlevi</span><span class="sxs-lookup"><span data-stu-id="c896d-102">Where function</span></span>

<span data-ttu-id="c896d-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c896d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c896d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c896d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c896d-105">Koşul ve dizi verildiğinde, koşulun true olduğu bu dizinin dizinlerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="c896d-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="c896d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c896d-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="c896d-107">koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c896d-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c896d-108">`'T`Öğeleri filtrelemek için kullanılan Boolean ile bir işlev.</span><span class="sxs-lookup"><span data-stu-id="c896d-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="c896d-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="c896d-109">array : 'T[]</span></span>

<span data-ttu-id="c896d-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="c896d-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="c896d-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c896d-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c896d-112">True olan bir dizin dizisi `predicate` .</span><span class="sxs-lookup"><span data-stu-id="c896d-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c896d-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c896d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c896d-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c896d-114">'T</span></span>

<span data-ttu-id="c896d-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="c896d-115">The type of `array` elements.</span></span>