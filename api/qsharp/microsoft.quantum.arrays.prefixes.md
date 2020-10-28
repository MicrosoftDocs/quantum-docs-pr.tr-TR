---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Ön ekler işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730063"
---
# <a name="prefixes-function"></a><span data-ttu-id="5eba7-102">Ön ekler işlevi</span><span class="sxs-lookup"><span data-stu-id="5eba7-102">Prefixes function</span></span>

<span data-ttu-id="5eba7-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5eba7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5eba7-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5eba7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5eba7-105">Bir dizi verildiğinde, tüm ön eklerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="5eba7-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="5eba7-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="5eba7-106">Description</span></span>

<span data-ttu-id="5eba7-107">Tüm öneklerin bir dizisini, yalnızca ilk öğesi olan Array öğesine kadar olan bir dizi ile başlayarak döndürür.</span><span class="sxs-lookup"><span data-stu-id="5eba7-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="5eba7-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="5eba7-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="5eba7-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="5eba7-109">array : 'T[]</span></span>

<span data-ttu-id="5eba7-110">Bir dizi öğe.</span><span class="sxs-lookup"><span data-stu-id="5eba7-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="5eba7-111">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="5eba7-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5eba7-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="5eba7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5eba7-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="5eba7-113">'T</span></span>

<span data-ttu-id="5eba7-114">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="5eba7-114">The type of `array` elements.</span></span>