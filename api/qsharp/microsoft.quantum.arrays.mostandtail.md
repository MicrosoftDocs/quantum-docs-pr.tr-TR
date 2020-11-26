---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220578"
---
# <a name="mostandtail-function"></a><span data-ttu-id="6bdb9-102">MostAndTail işlevi</span><span class="sxs-lookup"><span data-stu-id="6bdb9-102">MostAndTail function</span></span>

<span data-ttu-id="6bdb9-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6bdb9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6bdb9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6bdb9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6bdb9-105">Dizinin bir tanımlama grubu döndürür ve dizinin en son öğesidir.</span><span class="sxs-lookup"><span data-stu-id="6bdb9-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="6bdb9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6bdb9-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="6bdb9-107">dizi: ' A []</span><span class="sxs-lookup"><span data-stu-id="6bdb9-107">array : 'A[]</span></span>

<span data-ttu-id="6bdb9-108">En az bir öğesi olan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="6bdb9-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="6bdb9-109">Çıkış: (' A [], ' A)</span><span class="sxs-lookup"><span data-stu-id="6bdb9-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="6bdb9-110">Dizinin bir öğesi, bir ve en son öğesi.</span><span class="sxs-lookup"><span data-stu-id="6bdb9-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6bdb9-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="6bdb9-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="6bdb9-112">' A</span><span class="sxs-lookup"><span data-stu-id="6bdb9-112">'A</span></span>

<span data-ttu-id="6bdb9-113">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="6bdb9-113">The type of the array elements.</span></span>