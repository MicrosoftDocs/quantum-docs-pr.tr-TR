---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730407"
---
# <a name="columnat-function"></a><span data-ttu-id="131b3-102">ColumnAt işlevi</span><span class="sxs-lookup"><span data-stu-id="131b3-102">ColumnAt function</span></span>

<span data-ttu-id="131b3-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="131b3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="131b3-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="131b3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="131b3-105">Bir matrisi bir sütundan ayıklar.</span><span class="sxs-lookup"><span data-stu-id="131b3-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="131b3-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="131b3-106">Description</span></span>

<span data-ttu-id="131b3-107">Bu işlev, bir matrisi satır temelinde sırayla ayıklar.</span><span class="sxs-lookup"><span data-stu-id="131b3-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="131b3-108">Satır bağıntılarını ilk dizinin öğe erişimine ayıkladıktan sonra başka bir işleme gerek yoktur.</span><span class="sxs-lookup"><span data-stu-id="131b3-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="131b3-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="131b3-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="131b3-110">sütun: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="131b3-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="131b3-111">Matrisin sütunu</span><span class="sxs-lookup"><span data-stu-id="131b3-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="131b3-112">Matris: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="131b3-112">matrix : 'T[][]</span></span>

<span data-ttu-id="131b3-113">satır temelinde sıralı 2 boyutlu matris</span><span class="sxs-lookup"><span data-stu-id="131b3-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="131b3-114">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="131b3-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="131b3-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="131b3-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="131b3-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="131b3-116">'T</span></span>

<span data-ttu-id="131b3-117">Her öğesinin türü `matrix` .</span><span class="sxs-lookup"><span data-stu-id="131b3-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="131b3-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="131b3-118">See Also</span></span>

- [<span data-ttu-id="131b3-119">Microsoft. hisse. Arrays. Transdüğü</span><span class="sxs-lookup"><span data-stu-id="131b3-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="131b3-120">Microsoft. hisse. Arrays. köşegen</span><span class="sxs-lookup"><span data-stu-id="131b3-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)