---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: 4dd10b6e8839fd906ca9c2e36c89c626d5772149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220408"
---
# <a name="rest-function"></a><span data-ttu-id="2d510-102">Rest işlevi</span><span class="sxs-lookup"><span data-stu-id="2d510-102">Rest function</span></span>

<span data-ttu-id="2d510-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2d510-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2d510-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d510-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d510-105">İlk dizi öğesinin bırakılmasının dışında, bir giriş dizisine eşit olan bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="2d510-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2d510-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2d510-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="2d510-107">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="2d510-107">array : 'T[]</span></span>

<span data-ttu-id="2d510-108">İkinci-son öğelerine sahip bir dizi çıktı dizisini biçimlendirmek içindir.</span><span class="sxs-lookup"><span data-stu-id="2d510-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="2d510-109">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="2d510-109">Output : 'T[]</span></span>

<span data-ttu-id="2d510-110">Öğeleri içeren bir dizi `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="2d510-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2d510-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2d510-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2d510-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="2d510-112">'T</span></span>

<span data-ttu-id="2d510-113">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="2d510-113">The type of the array elements.</span></span>