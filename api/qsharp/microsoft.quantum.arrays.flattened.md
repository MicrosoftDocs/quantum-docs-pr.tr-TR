---
uid: Microsoft.Quantum.Arrays.Flattened
title: Düzleştirilmiş işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221224"
---
# <a name="flattened-function"></a><span data-ttu-id="ecd30-102">Düzleştirilmiş işlev</span><span class="sxs-lookup"><span data-stu-id="ecd30-102">Flattened function</span></span>

<span data-ttu-id="ecd30-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ecd30-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ecd30-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ecd30-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ecd30-105">Dizi dizileri verildiğinde, tüm dizilerin birleştirmesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="ecd30-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ecd30-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ecd30-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="ecd30-107">diziler: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="ecd30-107">arrays : 'T[][]</span></span>

<span data-ttu-id="ecd30-108">Dizi dizisi.</span><span class="sxs-lookup"><span data-stu-id="ecd30-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="ecd30-109">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="ecd30-109">Output : 'T[]</span></span>

<span data-ttu-id="ecd30-110">Tüm dizileri birleştirme.</span><span class="sxs-lookup"><span data-stu-id="ecd30-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ecd30-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ecd30-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ecd30-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ecd30-112">'T</span></span>

<span data-ttu-id="ecd30-113">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="ecd30-113">The type of `array` elements.</span></span>