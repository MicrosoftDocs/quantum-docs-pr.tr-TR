---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730218"
---
# <a name="indexof-function"></a><span data-ttu-id="ea3e5-102">IndexOf işlevi</span><span class="sxs-lookup"><span data-stu-id="ea3e5-102">IndexOf function</span></span>

<span data-ttu-id="ea3e5-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ea3e5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ea3e5-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea3e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea3e5-105">Belirli bir koşulu karşılayan dizideki ilk öğenin ilk dizinini döndürür.</span><span class="sxs-lookup"><span data-stu-id="ea3e5-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="ea3e5-106">Böyle bir öğe yoksa-1 döndürür.</span><span class="sxs-lookup"><span data-stu-id="ea3e5-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="ea3e5-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="ea3e5-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="ea3e5-108">koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ea3e5-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ea3e5-109">Dizi öğelerini davranan bir koşul işlevi.</span><span class="sxs-lookup"><span data-stu-id="ea3e5-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="ea3e5-110">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="ea3e5-110">arr : 'T[]</span></span>

<span data-ttu-id="ea3e5-111">Verilen koşul kullanılarak aranacak bir dizi.</span><span class="sxs-lookup"><span data-stu-id="ea3e5-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="ea3e5-112">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ea3e5-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ea3e5-113">En küçük dizin ya da `idx` `predicate(arr[idx])` böyle bir öğe yoksa-1.</span><span class="sxs-lookup"><span data-stu-id="ea3e5-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ea3e5-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ea3e5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ea3e5-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ea3e5-115">'T</span></span>

