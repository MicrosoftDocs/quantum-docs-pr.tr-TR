---
uid: Microsoft.Quantum.Arrays.Most
title: Çoğu işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 81e66e0b64ae8dfc44d163b68370ccadd191c729
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220612"
---
# <a name="most-function"></a><span data-ttu-id="9f0de-102">Çoğu işlev</span><span class="sxs-lookup"><span data-stu-id="9f0de-102">Most function</span></span>

<span data-ttu-id="9f0de-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9f0de-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9f0de-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f0de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9f0de-105">Son dizi öğesinin bırakılmasının dışında, bir giriş dizisine eşit olan bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="9f0de-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="9f0de-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9f0de-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="9f0de-107">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="9f0de-107">array : 'T[]</span></span>

<span data-ttu-id="9f0de-108">İlk olarak ikinci-son öğeleri olan bir dizi çıktı dizisini biçimlendirmek içindir.</span><span class="sxs-lookup"><span data-stu-id="9f0de-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="9f0de-109">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="9f0de-109">Output : 'T[]</span></span>

<span data-ttu-id="9f0de-110">Öğeleri içeren bir dizi `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="9f0de-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9f0de-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="9f0de-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9f0de-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="9f0de-112">'T</span></span>

<span data-ttu-id="9f0de-113">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="9f0de-113">The type of the array elements.</span></span>