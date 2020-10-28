---
uid: Microsoft.Quantum.Arrays.Excluding
title: İşlev hariç
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 8848c6e89da50efb4f7550168f1757b25a214a24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730287"
---
# <a name="excluding-function"></a><span data-ttu-id="4dde3-102">İşlev hariç</span><span class="sxs-lookup"><span data-stu-id="4dde3-102">Excluding function</span></span>

<span data-ttu-id="4dde3-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4dde3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4dde3-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4dde3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4dde3-105">Belirli bir dizin listesindeki öğeleri dışlayarak başka bir dizinin öğelerini içeren bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="4dde3-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="4dde3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4dde3-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="4dde3-107">Remove: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4dde3-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4dde3-108">Çıktının hangi öğelerin dışlanacağını belirten bir dizin dizisi.</span><span class="sxs-lookup"><span data-stu-id="4dde3-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="4dde3-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="4dde3-109">array : 'T[]</span></span>

<span data-ttu-id="4dde3-110">Çıkış dizisindeki değerlerin alındığı dizi.</span><span class="sxs-lookup"><span data-stu-id="4dde3-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="4dde3-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="4dde3-111">Output : 'T[]</span></span>

<span data-ttu-id="4dde3-112">Bu gibi bir dizi, `output` `output[0]` dizininin içinde görünmeyen ilk öğe, örneğin, `array` Bu gibi `remove` `output[1]` ikinci öğe ve benzeri.</span><span class="sxs-lookup"><span data-stu-id="4dde3-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4dde3-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="4dde3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4dde3-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="4dde3-114">'T</span></span>

<span data-ttu-id="4dde3-115">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="4dde3-115">The type of the array elements.</span></span>