---
uid: Microsoft.Quantum.Arrays.Most
title: Çoğu işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730103"
---
# <a name="most-function"></a><span data-ttu-id="8de2e-102">Çoğu işlev</span><span class="sxs-lookup"><span data-stu-id="8de2e-102">Most function</span></span>

<span data-ttu-id="8de2e-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8de2e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8de2e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8de2e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8de2e-105">Son dizi öğesinin bırakılmasının dışında, bir giriş dizisine eşit olan bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="8de2e-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="8de2e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8de2e-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="8de2e-107">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="8de2e-107">array : 'T[]</span></span>

<span data-ttu-id="8de2e-108">İlk olarak ikinci-son öğeleri olan bir dizi çıktı dizisini biçimlendirmek içindir.</span><span class="sxs-lookup"><span data-stu-id="8de2e-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="8de2e-109">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="8de2e-109">Output : 'T[]</span></span>

<span data-ttu-id="8de2e-110">Öğeleri içeren bir dizi `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="8de2e-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8de2e-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="8de2e-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8de2e-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="8de2e-112">'T</span></span>

<span data-ttu-id="8de2e-113">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="8de2e-113">The type of the array elements.</span></span>