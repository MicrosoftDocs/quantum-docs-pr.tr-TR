---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730047"
---
# <a name="rest-function"></a><span data-ttu-id="9f638-102">Rest işlevi</span><span class="sxs-lookup"><span data-stu-id="9f638-102">Rest function</span></span>

<span data-ttu-id="9f638-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9f638-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9f638-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9f638-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9f638-105">İlk dizi öğesinin bırakılmasının dışında, bir giriş dizisine eşit olan bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="9f638-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="9f638-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9f638-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="9f638-107">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="9f638-107">array : 'T[]</span></span>

<span data-ttu-id="9f638-108">İkinci-son öğelerine sahip bir dizi çıktı dizisini biçimlendirmek içindir.</span><span class="sxs-lookup"><span data-stu-id="9f638-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="9f638-109">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="9f638-109">Output : 'T[]</span></span>

<span data-ttu-id="9f638-110">Öğeleri içeren bir dizi `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="9f638-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9f638-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="9f638-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9f638-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="9f638-112">'T</span></span>

<span data-ttu-id="9f638-113">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="9f638-113">The type of the array elements.</span></span>