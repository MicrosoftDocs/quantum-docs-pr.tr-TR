---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Numaralandırılmış işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221428"
---
# <a name="enumerated-function"></a><span data-ttu-id="f5eeb-102">Numaralandırılmış işlev</span><span class="sxs-lookup"><span data-stu-id="f5eeb-102">Enumerated function</span></span>

<span data-ttu-id="f5eeb-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f5eeb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f5eeb-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5eeb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5eeb-105">Bir dizi verildiğinde, orijinal dizinin öğelerini içeren yeni bir dizi döndürür ve her bir öğenin indisleriyle birlikte.</span><span class="sxs-lookup"><span data-stu-id="f5eeb-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="f5eeb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f5eeb-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="f5eeb-107">dizi: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="f5eeb-107">array : 'TElement[]</span></span>

<span data-ttu-id="f5eeb-108">Öğeleri Numaralandırılacak olan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="f5eeb-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="f5eeb-109">Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int), ' TElement) []</span><span class="sxs-lookup"><span data-stu-id="f5eeb-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="f5eeb-110">Özgün dizinin öğelerini dizinleriyle birlikte içeren yeni bir dizi.</span><span class="sxs-lookup"><span data-stu-id="f5eeb-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f5eeb-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f5eeb-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="f5eeb-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="f5eeb-112">'TElement</span></span>

<span data-ttu-id="f5eeb-113">Dizinin öğe türü.</span><span class="sxs-lookup"><span data-stu-id="f5eeb-113">The type of elements of the array.</span></span>