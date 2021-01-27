---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845598"
---
# <a name="mostandtail-function"></a><span data-ttu-id="48ce5-102">MostAndTail işlevi</span><span class="sxs-lookup"><span data-stu-id="48ce5-102">MostAndTail function</span></span>

<span data-ttu-id="48ce5-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="48ce5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="48ce5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48ce5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48ce5-105">Dizinin bir tanımlama grubu döndürür ve dizinin en son öğesidir.</span><span class="sxs-lookup"><span data-stu-id="48ce5-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="48ce5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="48ce5-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="48ce5-107">dizi: ' A []</span><span class="sxs-lookup"><span data-stu-id="48ce5-107">array : 'A[]</span></span>

<span data-ttu-id="48ce5-108">En az bir öğesi olan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="48ce5-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="48ce5-109">Çıkış: (' A [], ' A)</span><span class="sxs-lookup"><span data-stu-id="48ce5-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="48ce5-110">Dizinin bir öğesi, bir ve en son öğesi.</span><span class="sxs-lookup"><span data-stu-id="48ce5-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="48ce5-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="48ce5-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="48ce5-112">' A</span><span class="sxs-lookup"><span data-stu-id="48ce5-112">'A</span></span>

<span data-ttu-id="48ce5-113">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="48ce5-113">The type of the array elements.</span></span>