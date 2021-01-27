---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848521"
---
# <a name="indexof-function"></a><span data-ttu-id="afb1e-102">IndexOf işlevi</span><span class="sxs-lookup"><span data-stu-id="afb1e-102">IndexOf function</span></span>

<span data-ttu-id="afb1e-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="afb1e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="afb1e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="afb1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="afb1e-105">Belirli bir koşulu karşılayan dizideki ilk öğenin ilk dizinini döndürür.</span><span class="sxs-lookup"><span data-stu-id="afb1e-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="afb1e-106">Böyle bir öğe yoksa-1 döndürür.</span><span class="sxs-lookup"><span data-stu-id="afb1e-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="afb1e-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="afb1e-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="afb1e-108">koşul: 'T-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="afb1e-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="afb1e-109">Dizi öğelerini davranan bir koşul işlevi.</span><span class="sxs-lookup"><span data-stu-id="afb1e-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="afb1e-110">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="afb1e-110">arr : 'T[]</span></span>

<span data-ttu-id="afb1e-111">Verilen koşul kullanılarak aranacak bir dizi.</span><span class="sxs-lookup"><span data-stu-id="afb1e-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="afb1e-112">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="afb1e-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="afb1e-113">En küçük dizin ya da `idx` `predicate(arr[idx])` böyle bir öğe yoksa-1.</span><span class="sxs-lookup"><span data-stu-id="afb1e-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="afb1e-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="afb1e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="afb1e-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="afb1e-115">'T</span></span>



## <a name="example"></a><span data-ttu-id="afb1e-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="afb1e-116">Example</span></span>

<span data-ttu-id="afb1e-117">Öğesinin `IsEven : Int -> Bool` `true` ve yalnızca girdisi çift ise, döndüren bir işlev olduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="afb1e-117">Suppose that `IsEven : Int -> Bool` is a function that returns `true` if and only if its input is even.</span></span> <span data-ttu-id="afb1e-118">Bu durumda, `IndexOf` bir dizideki ilk çift öğeyi bulmak için ile kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="afb1e-118">Then, this can be used with `IndexOf` to find the first even element in an array:</span></span>

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```