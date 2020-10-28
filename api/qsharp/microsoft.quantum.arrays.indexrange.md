---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Indexrange işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730202"
---
# <a name="indexrange-function"></a><span data-ttu-id="cbbf2-102">Indexrange işlevi</span><span class="sxs-lookup"><span data-stu-id="cbbf2-102">IndexRange function</span></span>

<span data-ttu-id="cbbf2-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cbbf2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cbbf2-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cbbf2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cbbf2-105">Bir dizi verildiğinde, for döngüsünde kullanılmak üzere uygun olan, bu dizinin dizinlerinin üzerinde bir Aralık döndürür.</span><span class="sxs-lookup"><span data-stu-id="cbbf2-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="cbbf2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="cbbf2-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="cbbf2-107">dizi: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="cbbf2-107">array : 'TElement[]</span></span>

<span data-ttu-id="cbbf2-108">Bir dizin aralığı döndürülmesi gereken dizi.</span><span class="sxs-lookup"><span data-stu-id="cbbf2-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="cbbf2-109">Çıkış: [Aralık](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="cbbf2-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="cbbf2-110">Dizinin tüm dizinleri üzerinde bir Aralık.</span><span class="sxs-lookup"><span data-stu-id="cbbf2-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cbbf2-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="cbbf2-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="cbbf2-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="cbbf2-112">'TElement</span></span>

<span data-ttu-id="cbbf2-113">Dizinin öğe türü.</span><span class="sxs-lookup"><span data-stu-id="cbbf2-113">The type of elements of the array.</span></span>