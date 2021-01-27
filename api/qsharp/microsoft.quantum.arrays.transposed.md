---
uid: Microsoft.Quantum.Arrays.Transposed
title: Dönüştürülmüş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850926"
---
# <a name="transposed-function"></a><span data-ttu-id="41a98-102">Dönüştürülmüş işlev</span><span class="sxs-lookup"><span data-stu-id="41a98-102">Transposed function</span></span>

<span data-ttu-id="41a98-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="41a98-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="41a98-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41a98-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41a98-105">Dizi dizisi olarak temsil edilen bir matrisin sırasını döndürür.</span><span class="sxs-lookup"><span data-stu-id="41a98-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="41a98-106">Description</span><span class="sxs-lookup"><span data-stu-id="41a98-106">Description</span></span>

<span data-ttu-id="41a98-107">$R $ Rows ve $c $ sütunları ile $r \times c $ matrisi olarak girin.</span><span class="sxs-lookup"><span data-stu-id="41a98-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="41a98-108">Matris satır tabanlıdır, yani `matrix[i][j]` $i $ ve column $j $ sütunundaki öğeye erişir.</span><span class="sxs-lookup"><span data-stu-id="41a98-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="41a98-109">Bu işlev, giriş matrisinin sırasını değiştir olan \times r $ matrisini $c döndürür.</span><span class="sxs-lookup"><span data-stu-id="41a98-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="41a98-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="41a98-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="41a98-111">Matris: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="41a98-111">matrix : 'T[][]</span></span>

<span data-ttu-id="41a98-112">Satır tabanlı $r \times c $ matrisi</span><span class="sxs-lookup"><span data-stu-id="41a98-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="41a98-113">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="41a98-113">Output : 'T[][]</span></span>

<span data-ttu-id="41a98-114">Dönüştürülmüş $c \times r $ matrisi</span><span class="sxs-lookup"><span data-stu-id="41a98-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="41a98-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="41a98-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="41a98-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="41a98-116">'T</span></span>

<span data-ttu-id="41a98-117">Her öğesinin türü `matrix` .</span><span class="sxs-lookup"><span data-stu-id="41a98-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="41a98-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="41a98-118">Example</span></span>

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```