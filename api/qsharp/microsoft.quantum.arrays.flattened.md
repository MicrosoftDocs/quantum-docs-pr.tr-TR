---
uid: Microsoft.Quantum.Arrays.Flattened
title: Düzleştirilmiş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 272533d4efd8598b21daa341c867c070a2083ce0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848628"
---
# <a name="flattened-function"></a><span data-ttu-id="f17e1-102">Düzleştirilmiş işlev</span><span class="sxs-lookup"><span data-stu-id="f17e1-102">Flattened function</span></span>

<span data-ttu-id="f17e1-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f17e1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f17e1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f17e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f17e1-105">Dizi dizileri verildiğinde, tüm dizilerin birleştirmesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="f17e1-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f17e1-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f17e1-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="f17e1-107">diziler: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="f17e1-107">arrays : 'T[][]</span></span>

<span data-ttu-id="f17e1-108">Dizi dizisi.</span><span class="sxs-lookup"><span data-stu-id="f17e1-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="f17e1-109">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="f17e1-109">Output : 'T[]</span></span>

<span data-ttu-id="f17e1-110">Tüm dizileri birleştirme.</span><span class="sxs-lookup"><span data-stu-id="f17e1-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f17e1-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f17e1-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f17e1-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f17e1-112">'T</span></span>

<span data-ttu-id="f17e1-113">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="f17e1-113">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="f17e1-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="f17e1-114">Example</span></span>

```qsharp
let flattened = Flattened([[1, 2], [3], [4, 5, 6]]);
// flattened = [1, 2, 3, 4, 5, 6]
```