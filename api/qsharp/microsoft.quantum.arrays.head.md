---
uid: Microsoft.Quantum.Arrays.Head
title: Head işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221122"
---
# <a name="head-function"></a><span data-ttu-id="a0a53-102">Head işlevi</span><span class="sxs-lookup"><span data-stu-id="a0a53-102">Head function</span></span>

<span data-ttu-id="a0a53-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a0a53-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a0a53-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a0a53-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a0a53-105">Dizinin ilk öğesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="a0a53-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="a0a53-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a0a53-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="a0a53-107">dizi: ' A []</span><span class="sxs-lookup"><span data-stu-id="a0a53-107">array : 'A[]</span></span>

<span data-ttu-id="a0a53-108">İlk öğenin alındığı dizi.</span><span class="sxs-lookup"><span data-stu-id="a0a53-108">Array of which the first element is taken.</span></span> <span data-ttu-id="a0a53-109">Dizi en az 1 uzunluğunda olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a0a53-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="a0a53-110">Çıkış: ' A</span><span class="sxs-lookup"><span data-stu-id="a0a53-110">Output : 'A</span></span>

<span data-ttu-id="a0a53-111">Dizinin ilk öğesi.</span><span class="sxs-lookup"><span data-stu-id="a0a53-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a0a53-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="a0a53-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="a0a53-113">' A</span><span class="sxs-lookup"><span data-stu-id="a0a53-113">'A</span></span>

<span data-ttu-id="a0a53-114">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="a0a53-114">The type of the array elements.</span></span>