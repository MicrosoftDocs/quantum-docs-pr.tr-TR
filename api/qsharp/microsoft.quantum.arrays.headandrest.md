---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730223"
---
# <a name="headandrest-function"></a><span data-ttu-id="a5693-102">HeadAndRest işlevi</span><span class="sxs-lookup"><span data-stu-id="a5693-102">HeadAndRest function</span></span>

<span data-ttu-id="a5693-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a5693-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a5693-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5693-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5693-105">Dizinin ilk ve kalan öğelerinin bir listesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="a5693-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="a5693-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a5693-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="a5693-107">dizi: ' A []</span><span class="sxs-lookup"><span data-stu-id="a5693-107">array : 'A[]</span></span>

<span data-ttu-id="a5693-108">En az bir öğesi olan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="a5693-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="a5693-109">Çıkış: (' A, ' A [])</span><span class="sxs-lookup"><span data-stu-id="a5693-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="a5693-110">Dizinin ilk ve kalan öğelerinin bir başlığı.</span><span class="sxs-lookup"><span data-stu-id="a5693-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a5693-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="a5693-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="a5693-112">' A</span><span class="sxs-lookup"><span data-stu-id="a5693-112">'A</span></span>

<span data-ttu-id="a5693-113">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="a5693-113">The type of the array elements.</span></span>