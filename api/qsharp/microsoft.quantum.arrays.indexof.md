---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: d63b204334611f8f2c3860f9ee1d756f637780e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221020"
---
# <a name="indexof-function"></a><span data-ttu-id="85675-102">IndexOf işlevi</span><span class="sxs-lookup"><span data-stu-id="85675-102">IndexOf function</span></span>

<span data-ttu-id="85675-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="85675-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="85675-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85675-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85675-105">Belirli bir koşulu karşılayan dizideki ilk öğenin ilk dizinini döndürür.</span><span class="sxs-lookup"><span data-stu-id="85675-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="85675-106">Böyle bir öğe yoksa-1 döndürür.</span><span class="sxs-lookup"><span data-stu-id="85675-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="85675-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="85675-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="85675-108">koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="85675-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="85675-109">Dizi öğelerini davranan bir koşul işlevi.</span><span class="sxs-lookup"><span data-stu-id="85675-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="85675-110">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="85675-110">arr : 'T[]</span></span>

<span data-ttu-id="85675-111">Verilen koşul kullanılarak aranacak bir dizi.</span><span class="sxs-lookup"><span data-stu-id="85675-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="85675-112">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="85675-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="85675-113">En küçük dizin ya da `idx` `predicate(arr[idx])` böyle bir öğe yoksa-1.</span><span class="sxs-lookup"><span data-stu-id="85675-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="85675-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="85675-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="85675-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="85675-115">'T</span></span>

