---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Numaralandırılmış işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848136"
---
# <a name="enumerated-function"></a><span data-ttu-id="34427-102">Numaralandırılmış işlev</span><span class="sxs-lookup"><span data-stu-id="34427-102">Enumerated function</span></span>

<span data-ttu-id="34427-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="34427-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="34427-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34427-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34427-105">Bir dizi verildiğinde, orijinal dizinin öğelerini içeren yeni bir dizi döndürür ve her bir öğenin indisleriyle birlikte.</span><span class="sxs-lookup"><span data-stu-id="34427-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="34427-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="34427-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="34427-107">dizi: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="34427-107">array : 'TElement[]</span></span>

<span data-ttu-id="34427-108">Öğeleri Numaralandırılacak olan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="34427-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="34427-109">Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int), ' TElement) []</span><span class="sxs-lookup"><span data-stu-id="34427-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="34427-110">Özgün dizinin öğelerini dizinleriyle birlikte içeren yeni bir dizi.</span><span class="sxs-lookup"><span data-stu-id="34427-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="34427-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="34427-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="34427-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="34427-112">'TElement</span></span>

<span data-ttu-id="34427-113">Dizinin öğe türü.</span><span class="sxs-lookup"><span data-stu-id="34427-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="34427-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="34427-114">Example</span></span>

<span data-ttu-id="34427-115">Aşağıdaki `for` döngüler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="34427-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```