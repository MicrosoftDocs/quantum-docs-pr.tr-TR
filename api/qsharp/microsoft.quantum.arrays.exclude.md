---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848672"
---
# <a name="exclude-function"></a><span data-ttu-id="9212a-102">Exclude işlevi</span><span class="sxs-lookup"><span data-stu-id="9212a-102">Exclude function</span></span>

<span data-ttu-id="9212a-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9212a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9212a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9212a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9212a-105">Belirli bir dizin listesindeki öğeleri dışlayarak başka bir dizinin öğelerini içeren bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="9212a-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="9212a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9212a-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="9212a-107">Remove: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9212a-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9212a-108">Çıktının hangi öğelerin dışlanacağını belirten bir dizin dizisi.</span><span class="sxs-lookup"><span data-stu-id="9212a-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="9212a-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="9212a-109">array : 'T[]</span></span>

<span data-ttu-id="9212a-110">Çıkış dizisindeki değerlerin alındığı dizi.</span><span class="sxs-lookup"><span data-stu-id="9212a-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="9212a-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="9212a-111">Output : 'T[]</span></span>

<span data-ttu-id="9212a-112">Bu gibi bir dizi, `output` `output[0]` dizininin içinde görünmeyen ilk öğe, örneğin, `array` Bu gibi `remove` `output[1]` ikinci öğe ve benzeri.</span><span class="sxs-lookup"><span data-stu-id="9212a-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9212a-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="9212a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9212a-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="9212a-114">'T</span></span>

<span data-ttu-id="9212a-115">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="9212a-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="9212a-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="9212a-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```