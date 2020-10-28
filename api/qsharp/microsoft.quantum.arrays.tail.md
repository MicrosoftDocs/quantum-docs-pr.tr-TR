---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729983"
---
# <a name="tail-function"></a><span data-ttu-id="7de18-102">Tail işlevi</span><span class="sxs-lookup"><span data-stu-id="7de18-102">Tail function</span></span>

<span data-ttu-id="7de18-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7de18-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7de18-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7de18-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7de18-105">Dizinin son öğesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="7de18-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="7de18-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7de18-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="7de18-107">dizi: ' A []</span><span class="sxs-lookup"><span data-stu-id="7de18-107">array : 'A[]</span></span>

<span data-ttu-id="7de18-108">Son öğenin alındığı dizi.</span><span class="sxs-lookup"><span data-stu-id="7de18-108">Array of which the last element is taken.</span></span> <span data-ttu-id="7de18-109">Dizi en az 1 uzunluğunda olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="7de18-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="7de18-110">Çıkış: ' A</span><span class="sxs-lookup"><span data-stu-id="7de18-110">Output : 'A</span></span>

<span data-ttu-id="7de18-111">Dizinin son öğesi.</span><span class="sxs-lookup"><span data-stu-id="7de18-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7de18-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="7de18-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="7de18-113">' A</span><span class="sxs-lookup"><span data-stu-id="7de18-113">'A</span></span>

<span data-ttu-id="7de18-114">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="7de18-114">The type of the array elements.</span></span>