---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: b6c579df354185a2defb08cd78bce816d8cc5959
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845470"
---
# <a name="rest-function"></a><span data-ttu-id="ecb4b-102">Rest işlevi</span><span class="sxs-lookup"><span data-stu-id="ecb4b-102">Rest function</span></span>

<span data-ttu-id="ecb4b-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ecb4b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ecb4b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ecb4b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ecb4b-105">İlk dizi öğesinin bırakılmasının dışında, bir giriş dizisine eşit olan bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="ecb4b-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ecb4b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ecb4b-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="ecb4b-107">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="ecb4b-107">array : 'T[]</span></span>

<span data-ttu-id="ecb4b-108">İkinci-son öğelerine sahip bir dizi çıktı dizisini biçimlendirmek içindir.</span><span class="sxs-lookup"><span data-stu-id="ecb4b-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="ecb4b-109">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="ecb4b-109">Output : 'T[]</span></span>

<span data-ttu-id="ecb4b-110">Öğeleri içeren bir dizi `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="ecb4b-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ecb4b-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ecb4b-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ecb4b-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ecb4b-112">'T</span></span>

<span data-ttu-id="ecb4b-113">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="ecb4b-113">The type of the array elements.</span></span>