---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Köşegen işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730359"
---
# <a name="diagonal-function"></a><span data-ttu-id="ccd33-102">Köşegen işlev</span><span class="sxs-lookup"><span data-stu-id="ccd33-102">Diagonal function</span></span>

<span data-ttu-id="ccd33-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ccd33-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ccd33-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ccd33-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ccd33-105">2 boyutlu bir dizinin köşegen öğelerinin dizisini döndürür</span><span class="sxs-lookup"><span data-stu-id="ccd33-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="ccd33-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ccd33-106">Description</span></span>

<span data-ttu-id="ccd33-107">2 boyutlu dizide kare şekli yoksa, en az satır ve sütun sayısına göre aşağı köşegen döndürülür.</span><span class="sxs-lookup"><span data-stu-id="ccd33-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="ccd33-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="ccd33-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="ccd33-109">Matris: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="ccd33-109">matrix : 'T[][]</span></span>

<span data-ttu-id="ccd33-110">satır temelinde sıralı 2 boyutlu matris</span><span class="sxs-lookup"><span data-stu-id="ccd33-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="ccd33-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="ccd33-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ccd33-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ccd33-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ccd33-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ccd33-113">'T</span></span>

<span data-ttu-id="ccd33-114">Her öğesinin türü `matrix` .</span><span class="sxs-lookup"><span data-stu-id="ccd33-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccd33-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ccd33-115">See Also</span></span>

- [<span data-ttu-id="ccd33-116">Microsoft. hisse. Arrays. Transdüğü</span><span class="sxs-lookup"><span data-stu-id="ccd33-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)