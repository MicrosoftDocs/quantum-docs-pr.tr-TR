---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Indexrange işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845790"
---
# <a name="indexrange-function"></a><span data-ttu-id="7ebe7-102">Indexrange işlevi</span><span class="sxs-lookup"><span data-stu-id="7ebe7-102">IndexRange function</span></span>

<span data-ttu-id="7ebe7-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7ebe7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7ebe7-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7ebe7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7ebe7-105">Bir dizi verildiğinde, for döngüsünde kullanılmak üzere uygun olan, bu dizinin dizinlerinin üzerinde bir Aralık döndürür.</span><span class="sxs-lookup"><span data-stu-id="7ebe7-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="7ebe7-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7ebe7-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="7ebe7-107">dizi: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="7ebe7-107">array : 'TElement[]</span></span>

<span data-ttu-id="7ebe7-108">Bir dizin aralığı döndürülmesi gereken dizi.</span><span class="sxs-lookup"><span data-stu-id="7ebe7-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="7ebe7-109">Çıkış: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="7ebe7-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="7ebe7-110">Dizinin tüm dizinleri üzerinde bir Aralık.</span><span class="sxs-lookup"><span data-stu-id="7ebe7-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7ebe7-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="7ebe7-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="7ebe7-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="7ebe7-112">'TElement</span></span>

<span data-ttu-id="7ebe7-113">Dizinin öğe türü.</span><span class="sxs-lookup"><span data-stu-id="7ebe7-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="7ebe7-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="7ebe7-114">Example</span></span>

<span data-ttu-id="7ebe7-115">Aşağıdaki `for` döngüler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="7ebe7-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```