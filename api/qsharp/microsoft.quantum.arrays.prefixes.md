---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Ön ekler işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845505"
---
# <a name="prefixes-function"></a><span data-ttu-id="43dde-102">Ön ekler işlevi</span><span class="sxs-lookup"><span data-stu-id="43dde-102">Prefixes function</span></span>

<span data-ttu-id="43dde-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="43dde-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="43dde-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="43dde-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="43dde-105">Bir dizi verildiğinde, tüm ön eklerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="43dde-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="43dde-106">Description</span><span class="sxs-lookup"><span data-stu-id="43dde-106">Description</span></span>

<span data-ttu-id="43dde-107">Tüm öneklerin bir dizisini, yalnızca ilk öğesi olan Array öğesine kadar olan bir dizi ile başlayarak döndürür.</span><span class="sxs-lookup"><span data-stu-id="43dde-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="43dde-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="43dde-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="43dde-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="43dde-109">array : 'T[]</span></span>

<span data-ttu-id="43dde-110">Bir dizi öğe.</span><span class="sxs-lookup"><span data-stu-id="43dde-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="43dde-111">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="43dde-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="43dde-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="43dde-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="43dde-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="43dde-113">'T</span></span>

<span data-ttu-id="43dde-114">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="43dde-114">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="43dde-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="43dde-115">Example</span></span>

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```