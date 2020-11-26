---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 4ea0d754fce4fc7e3e4e42e55b56720cb3f95ca6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221360"
---
# <a name="exclude-function"></a><span data-ttu-id="fae3a-102">Exclude işlevi</span><span class="sxs-lookup"><span data-stu-id="fae3a-102">Exclude function</span></span>

<span data-ttu-id="fae3a-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fae3a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fae3a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fae3a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fae3a-105">Belirli bir dizin listesindeki öğeleri dışlayarak başka bir dizinin öğelerini içeren bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="fae3a-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="fae3a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="fae3a-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="fae3a-107">Remove: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fae3a-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fae3a-108">Çıktının hangi öğelerin dışlanacağını belirten bir dizin dizisi.</span><span class="sxs-lookup"><span data-stu-id="fae3a-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="fae3a-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="fae3a-109">array : 'T[]</span></span>

<span data-ttu-id="fae3a-110">Çıkış dizisindeki değerlerin alındığı dizi.</span><span class="sxs-lookup"><span data-stu-id="fae3a-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="fae3a-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="fae3a-111">Output : 'T[]</span></span>

<span data-ttu-id="fae3a-112">Bu gibi bir dizi, `output` `output[0]` dizininin içinde görünmeyen ilk öğe, örneğin, `array` Bu gibi `remove` `output[1]` ikinci öğe ve benzeri.</span><span class="sxs-lookup"><span data-stu-id="fae3a-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fae3a-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="fae3a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fae3a-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="fae3a-114">'T</span></span>

<span data-ttu-id="fae3a-115">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="fae3a-115">The type of the array elements.</span></span>