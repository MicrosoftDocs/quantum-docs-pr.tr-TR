---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730290"
---
# <a name="exclude-function"></a><span data-ttu-id="58b56-102">Exclude işlevi</span><span class="sxs-lookup"><span data-stu-id="58b56-102">Exclude function</span></span>

<span data-ttu-id="58b56-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="58b56-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="58b56-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="58b56-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="58b56-105">Belirli bir dizin listesindeki öğeleri dışlayarak başka bir dizinin öğelerini içeren bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="58b56-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="58b56-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="58b56-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="58b56-107">Remove: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="58b56-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="58b56-108">Çıktının hangi öğelerin dışlanacağını belirten bir dizin dizisi.</span><span class="sxs-lookup"><span data-stu-id="58b56-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="58b56-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="58b56-109">array : 'T[]</span></span>

<span data-ttu-id="58b56-110">Çıkış dizisindeki değerlerin alındığı dizi.</span><span class="sxs-lookup"><span data-stu-id="58b56-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="58b56-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="58b56-111">Output : 'T[]</span></span>

<span data-ttu-id="58b56-112">Bu gibi bir dizi, `output` `output[0]` dizininin içinde görünmeyen ilk öğe, örneğin, `array` Bu gibi `remove` `output[1]` ikinci öğe ve benzeri.</span><span class="sxs-lookup"><span data-stu-id="58b56-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="58b56-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="58b56-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="58b56-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="58b56-114">'T</span></span>

<span data-ttu-id="58b56-115">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="58b56-115">The type of the array elements.</span></span>