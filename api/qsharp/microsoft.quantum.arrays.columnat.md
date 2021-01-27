---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846267"
---
# <a name="columnat-function"></a><span data-ttu-id="2df29-102">ColumnAt işlevi</span><span class="sxs-lookup"><span data-stu-id="2df29-102">ColumnAt function</span></span>

<span data-ttu-id="2df29-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2df29-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2df29-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2df29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2df29-105">Bir matrisi bir sütundan ayıklar.</span><span class="sxs-lookup"><span data-stu-id="2df29-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="2df29-106">Description</span><span class="sxs-lookup"><span data-stu-id="2df29-106">Description</span></span>

<span data-ttu-id="2df29-107">Bu işlev, bir matrisi satır temelinde sırayla ayıklar.</span><span class="sxs-lookup"><span data-stu-id="2df29-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="2df29-108">Satır bağıntılarını ilk dizinin öğe erişimine ayıkladıktan sonra başka bir işleme gerek yoktur.</span><span class="sxs-lookup"><span data-stu-id="2df29-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="2df29-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="2df29-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="2df29-110">sütun: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2df29-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2df29-111">Matrisin sütunu</span><span class="sxs-lookup"><span data-stu-id="2df29-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="2df29-112">Matris: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="2df29-112">matrix : 'T[][]</span></span>

<span data-ttu-id="2df29-113">satır temelinde sıralı 2 boyutlu matris</span><span class="sxs-lookup"><span data-stu-id="2df29-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="2df29-114">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="2df29-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2df29-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2df29-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2df29-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="2df29-116">'T</span></span>

<span data-ttu-id="2df29-117">Her öğesinin türü `matrix` .</span><span class="sxs-lookup"><span data-stu-id="2df29-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="2df29-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="2df29-118">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a><span data-ttu-id="2df29-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2df29-119">See Also</span></span>

- [<span data-ttu-id="2df29-120">Microsoft. hisse. Arrays. Transdüğü</span><span class="sxs-lookup"><span data-stu-id="2df29-120">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="2df29-121">Microsoft. hisse. Arrays. köşegen</span><span class="sxs-lookup"><span data-stu-id="2df29-121">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)