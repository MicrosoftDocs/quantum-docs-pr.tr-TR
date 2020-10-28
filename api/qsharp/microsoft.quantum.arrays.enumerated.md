---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Numaralandırılmış işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730306"
---
# <a name="enumerated-function"></a><span data-ttu-id="de686-102">Numaralandırılmış işlev</span><span class="sxs-lookup"><span data-stu-id="de686-102">Enumerated function</span></span>

<span data-ttu-id="de686-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="de686-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="de686-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de686-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de686-105">Bir dizi verildiğinde, orijinal dizinin öğelerini içeren yeni bir dizi döndürür ve her bir öğenin indisleriyle birlikte.</span><span class="sxs-lookup"><span data-stu-id="de686-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="de686-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="de686-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="de686-107">dizi: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="de686-107">array : 'TElement[]</span></span>

<span data-ttu-id="de686-108">Öğeleri Numaralandırılacak olan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="de686-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="de686-109">Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int), ' TElement) []</span><span class="sxs-lookup"><span data-stu-id="de686-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="de686-110">Özgün dizinin öğelerini dizinleriyle birlikte içeren yeni bir dizi.</span><span class="sxs-lookup"><span data-stu-id="de686-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="de686-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="de686-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="de686-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="de686-112">'TElement</span></span>

<span data-ttu-id="de686-113">Dizinin öğe türü.</span><span class="sxs-lookup"><span data-stu-id="de686-113">The type of elements of the array.</span></span>