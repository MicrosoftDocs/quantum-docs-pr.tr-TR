---
uid: Microsoft.Quantum.Arrays.Head
title: Head işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848568"
---
# <a name="head-function"></a><span data-ttu-id="74099-102">Head işlevi</span><span class="sxs-lookup"><span data-stu-id="74099-102">Head function</span></span>

<span data-ttu-id="74099-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="74099-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="74099-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="74099-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="74099-105">Dizinin ilk öğesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="74099-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="74099-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="74099-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="74099-107">dizi: ' A []</span><span class="sxs-lookup"><span data-stu-id="74099-107">array : 'A[]</span></span>

<span data-ttu-id="74099-108">İlk öğenin alındığı dizi.</span><span class="sxs-lookup"><span data-stu-id="74099-108">Array of which the first element is taken.</span></span> <span data-ttu-id="74099-109">Dizi en az 1 uzunluğunda olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="74099-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="74099-110">Çıkış: ' A</span><span class="sxs-lookup"><span data-stu-id="74099-110">Output : 'A</span></span>

<span data-ttu-id="74099-111">Dizinin ilk öğesi.</span><span class="sxs-lookup"><span data-stu-id="74099-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="74099-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="74099-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="74099-113">' A</span><span class="sxs-lookup"><span data-stu-id="74099-113">'A</span></span>

<span data-ttu-id="74099-114">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="74099-114">The type of the array elements.</span></span>