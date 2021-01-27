---
uid: Microsoft.Quantum.Arrays.Where
title: WHERE işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842213"
---
# <a name="where-function"></a><span data-ttu-id="e7dae-102">WHERE işlevi</span><span class="sxs-lookup"><span data-stu-id="e7dae-102">Where function</span></span>

<span data-ttu-id="e7dae-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e7dae-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e7dae-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7dae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7dae-105">Koşul ve dizi verildiğinde, koşulun true olduğu bu dizinin dizinlerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="e7dae-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="e7dae-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e7dae-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="e7dae-107">koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e7dae-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e7dae-108">`'T`Öğeleri filtrelemek için kullanılan Boolean ile bir işlev.</span><span class="sxs-lookup"><span data-stu-id="e7dae-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="e7dae-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="e7dae-109">array : 'T[]</span></span>

<span data-ttu-id="e7dae-110">Öğesinden bir dizi öğe `'T` .</span><span class="sxs-lookup"><span data-stu-id="e7dae-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="e7dae-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e7dae-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e7dae-112">True olan bir dizin dizisi `predicate` .</span><span class="sxs-lookup"><span data-stu-id="e7dae-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e7dae-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e7dae-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e7dae-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e7dae-114">'T</span></span>

<span data-ttu-id="e7dae-115">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="e7dae-115">The type of `array` elements.</span></span>