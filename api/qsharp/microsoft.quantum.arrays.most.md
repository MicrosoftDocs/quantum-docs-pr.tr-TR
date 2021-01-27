---
uid: Microsoft.Quantum.Arrays.Most
title: Çoğu işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845574"
---
# <a name="most-function"></a><span data-ttu-id="3dd76-102">Çoğu işlev</span><span class="sxs-lookup"><span data-stu-id="3dd76-102">Most function</span></span>

<span data-ttu-id="3dd76-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3dd76-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3dd76-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3dd76-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3dd76-105">Son dizi öğesinin bırakılmasının dışında, bir giriş dizisine eşit olan bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="3dd76-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="3dd76-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3dd76-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="3dd76-107">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="3dd76-107">array : 'T[]</span></span>

<span data-ttu-id="3dd76-108">İlk olarak ikinci-son öğeleri olan bir dizi çıktı dizisini biçimlendirmek içindir.</span><span class="sxs-lookup"><span data-stu-id="3dd76-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="3dd76-109">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="3dd76-109">Output : 'T[]</span></span>

<span data-ttu-id="3dd76-110">Öğeleri içeren bir dizi `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="3dd76-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3dd76-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="3dd76-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3dd76-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="3dd76-112">'T</span></span>

<span data-ttu-id="3dd76-113">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="3dd76-113">The type of the array elements.</span></span>