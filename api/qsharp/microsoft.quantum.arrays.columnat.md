---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210122"
---
# <a name="columnat-function"></a><span data-ttu-id="4d983-102">ColumnAt işlevi</span><span class="sxs-lookup"><span data-stu-id="4d983-102">ColumnAt function</span></span>

<span data-ttu-id="4d983-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4d983-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4d983-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d983-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d983-105">Bir matrisi bir sütundan ayıklar.</span><span class="sxs-lookup"><span data-stu-id="4d983-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="4d983-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4d983-106">Description</span></span>

<span data-ttu-id="4d983-107">Bu işlev, bir matrisi satır temelinde sırayla ayıklar.</span><span class="sxs-lookup"><span data-stu-id="4d983-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="4d983-108">Satır bağıntılarını ilk dizinin öğe erişimine ayıkladıktan sonra başka bir işleme gerek yoktur.</span><span class="sxs-lookup"><span data-stu-id="4d983-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="4d983-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="4d983-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="4d983-110">sütun: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d983-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4d983-111">Matrisin sütunu</span><span class="sxs-lookup"><span data-stu-id="4d983-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="4d983-112">Matris: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="4d983-112">matrix : 'T[][]</span></span>

<span data-ttu-id="4d983-113">satır temelinde sıralı 2 boyutlu matris</span><span class="sxs-lookup"><span data-stu-id="4d983-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="4d983-114">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="4d983-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4d983-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="4d983-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4d983-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="4d983-116">'T</span></span>

<span data-ttu-id="4d983-117">Her öğesinin türü `matrix` .</span><span class="sxs-lookup"><span data-stu-id="4d983-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d983-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4d983-118">See Also</span></span>

- [<span data-ttu-id="4d983-119">Microsoft. hisse. Arrays. Transdüğü</span><span class="sxs-lookup"><span data-stu-id="4d983-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="4d983-120">Microsoft. hisse. Arrays. köşegen</span><span class="sxs-lookup"><span data-stu-id="4d983-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)