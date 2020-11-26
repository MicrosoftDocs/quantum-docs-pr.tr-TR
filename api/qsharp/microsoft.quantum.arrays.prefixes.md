---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Ön ekler işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220407"
---
# <a name="prefixes-function"></a><span data-ttu-id="f53dc-102">Ön ekler işlevi</span><span class="sxs-lookup"><span data-stu-id="f53dc-102">Prefixes function</span></span>

<span data-ttu-id="f53dc-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f53dc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f53dc-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f53dc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f53dc-105">Bir dizi verildiğinde, tüm ön eklerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="f53dc-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="f53dc-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f53dc-106">Description</span></span>

<span data-ttu-id="f53dc-107">Tüm öneklerin bir dizisini, yalnızca ilk öğesi olan Array öğesine kadar olan bir dizi ile başlayarak döndürür.</span><span class="sxs-lookup"><span data-stu-id="f53dc-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="f53dc-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="f53dc-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="f53dc-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="f53dc-109">array : 'T[]</span></span>

<span data-ttu-id="f53dc-110">Bir dizi öğe.</span><span class="sxs-lookup"><span data-stu-id="f53dc-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="f53dc-111">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="f53dc-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f53dc-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f53dc-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f53dc-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f53dc-113">'T</span></span>

<span data-ttu-id="f53dc-114">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="f53dc-114">The type of `array` elements.</span></span>