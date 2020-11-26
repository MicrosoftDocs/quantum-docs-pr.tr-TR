---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220102"
---
# <a name="tail-function"></a><span data-ttu-id="9a025-102">Tail işlevi</span><span class="sxs-lookup"><span data-stu-id="9a025-102">Tail function</span></span>

<span data-ttu-id="9a025-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9a025-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9a025-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a025-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a025-105">Dizinin son öğesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="9a025-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="9a025-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9a025-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="9a025-107">dizi: ' A []</span><span class="sxs-lookup"><span data-stu-id="9a025-107">array : 'A[]</span></span>

<span data-ttu-id="9a025-108">Son öğenin alındığı dizi.</span><span class="sxs-lookup"><span data-stu-id="9a025-108">Array of which the last element is taken.</span></span> <span data-ttu-id="9a025-109">Dizi en az 1 uzunluğunda olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9a025-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="9a025-110">Çıkış: ' A</span><span class="sxs-lookup"><span data-stu-id="9a025-110">Output : 'A</span></span>

<span data-ttu-id="9a025-111">Dizinin son öğesi.</span><span class="sxs-lookup"><span data-stu-id="9a025-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9a025-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="9a025-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="9a025-113">' A</span><span class="sxs-lookup"><span data-stu-id="9a025-113">'A</span></span>

<span data-ttu-id="9a025-114">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="9a025-114">The type of the array elements.</span></span>