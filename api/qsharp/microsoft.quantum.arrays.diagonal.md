---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Köşegen işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221547"
---
# <a name="diagonal-function"></a><span data-ttu-id="807e5-102">Köşegen işlev</span><span class="sxs-lookup"><span data-stu-id="807e5-102">Diagonal function</span></span>

<span data-ttu-id="807e5-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="807e5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="807e5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="807e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="807e5-105">2 boyutlu bir dizinin köşegen öğelerinin dizisini döndürür</span><span class="sxs-lookup"><span data-stu-id="807e5-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="807e5-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="807e5-106">Description</span></span>

<span data-ttu-id="807e5-107">2 boyutlu dizide kare şekli yoksa, en az satır ve sütun sayısına göre aşağı köşegen döndürülür.</span><span class="sxs-lookup"><span data-stu-id="807e5-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="807e5-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="807e5-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="807e5-109">Matris: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="807e5-109">matrix : 'T[][]</span></span>

<span data-ttu-id="807e5-110">satır temelinde sıralı 2 boyutlu matris</span><span class="sxs-lookup"><span data-stu-id="807e5-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="807e5-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="807e5-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="807e5-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="807e5-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="807e5-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="807e5-113">'T</span></span>

<span data-ttu-id="807e5-114">Her öğesinin türü `matrix` .</span><span class="sxs-lookup"><span data-stu-id="807e5-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="807e5-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="807e5-115">See Also</span></span>

- [<span data-ttu-id="807e5-116">Microsoft. hisse. Arrays. Transdüğü</span><span class="sxs-lookup"><span data-stu-id="807e5-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)