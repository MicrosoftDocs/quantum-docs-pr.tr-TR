---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730098"
---
# <a name="mostandtail-function"></a><span data-ttu-id="50926-102">MostAndTail işlevi</span><span class="sxs-lookup"><span data-stu-id="50926-102">MostAndTail function</span></span>

<span data-ttu-id="50926-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="50926-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="50926-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50926-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50926-105">Dizinin bir tanımlama grubu döndürür ve dizinin en son öğesidir.</span><span class="sxs-lookup"><span data-stu-id="50926-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="50926-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="50926-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="50926-107">dizi: ' A []</span><span class="sxs-lookup"><span data-stu-id="50926-107">array : 'A[]</span></span>

<span data-ttu-id="50926-108">En az bir öğesi olan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="50926-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="50926-109">Çıkış: (' A [], ' A)</span><span class="sxs-lookup"><span data-stu-id="50926-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="50926-110">Dizinin bir öğesi, bir ve en son öğesi.</span><span class="sxs-lookup"><span data-stu-id="50926-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="50926-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="50926-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="50926-112">' A</span><span class="sxs-lookup"><span data-stu-id="50926-112">'A</span></span>

<span data-ttu-id="50926-113">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="50926-113">The type of the array elements.</span></span>