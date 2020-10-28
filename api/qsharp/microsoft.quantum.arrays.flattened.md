---
uid: Microsoft.Quantum.Arrays.Flattened
title: Düzleştirilmiş işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730263"
---
# <a name="flattened-function"></a><span data-ttu-id="82906-102">Düzleştirilmiş işlev</span><span class="sxs-lookup"><span data-stu-id="82906-102">Flattened function</span></span>

<span data-ttu-id="82906-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="82906-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="82906-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82906-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82906-105">Dizi dizileri verildiğinde, tüm dizilerin birleştirmesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="82906-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="82906-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="82906-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="82906-107">diziler: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="82906-107">arrays : 'T[][]</span></span>

<span data-ttu-id="82906-108">Dizi dizisi.</span><span class="sxs-lookup"><span data-stu-id="82906-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="82906-109">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="82906-109">Output : 'T[]</span></span>

<span data-ttu-id="82906-110">Tüm dizileri birleştirme.</span><span class="sxs-lookup"><span data-stu-id="82906-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="82906-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="82906-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="82906-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="82906-112">'T</span></span>

<span data-ttu-id="82906-113">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="82906-113">The type of `array` elements.</span></span>