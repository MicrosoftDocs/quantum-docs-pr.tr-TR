---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Indexrange işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220952"
---
# <a name="indexrange-function"></a><span data-ttu-id="ab475-102">Indexrange işlevi</span><span class="sxs-lookup"><span data-stu-id="ab475-102">IndexRange function</span></span>

<span data-ttu-id="ab475-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ab475-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ab475-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ab475-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ab475-105">Bir dizi verildiğinde, for döngüsünde kullanılmak üzere uygun olan, bu dizinin dizinlerinin üzerinde bir Aralık döndürür.</span><span class="sxs-lookup"><span data-stu-id="ab475-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="ab475-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ab475-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="ab475-107">dizi: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="ab475-107">array : 'TElement[]</span></span>

<span data-ttu-id="ab475-108">Bir dizin aralığı döndürülmesi gereken dizi.</span><span class="sxs-lookup"><span data-stu-id="ab475-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="ab475-109">Çıkış: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="ab475-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="ab475-110">Dizinin tüm dizinleri üzerinde bir Aralık.</span><span class="sxs-lookup"><span data-stu-id="ab475-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ab475-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ab475-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="ab475-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="ab475-112">'TElement</span></span>

<span data-ttu-id="ab475-113">Dizinin öğe türü.</span><span class="sxs-lookup"><span data-stu-id="ab475-113">The type of elements of the array.</span></span>