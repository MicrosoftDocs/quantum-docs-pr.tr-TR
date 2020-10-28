---
uid: Microsoft.Quantum.Arrays.Transposed
title: Dönüştürülmüş işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729978"
---
# <a name="transposed-function"></a><span data-ttu-id="d7ddc-102">Dönüştürülmüş işlev</span><span class="sxs-lookup"><span data-stu-id="d7ddc-102">Transposed function</span></span>

<span data-ttu-id="d7ddc-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d7ddc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d7ddc-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d7ddc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d7ddc-105">Dizi dizisi olarak temsil edilen bir matrisin sırasını döndürür.</span><span class="sxs-lookup"><span data-stu-id="d7ddc-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="d7ddc-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="d7ddc-106">Description</span></span>

<span data-ttu-id="d7ddc-107">$R $ Rows ve $c $ sütunları ile $r \times c $ matrisi olarak girin.</span><span class="sxs-lookup"><span data-stu-id="d7ddc-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="d7ddc-108">Matris satır tabanlıdır, yani `matrix[i][j]` $i $ ve column $j $ sütunundaki öğeye erişir.</span><span class="sxs-lookup"><span data-stu-id="d7ddc-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="d7ddc-109">Bu işlev, giriş matrisinin sırasını değiştir olan \times r $ matrisini $c döndürür.</span><span class="sxs-lookup"><span data-stu-id="d7ddc-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="d7ddc-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="d7ddc-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="d7ddc-111">Matris: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="d7ddc-111">matrix : 'T[][]</span></span>

<span data-ttu-id="d7ddc-112">Satır tabanlı $r \times c $ matrisi</span><span class="sxs-lookup"><span data-stu-id="d7ddc-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="d7ddc-113">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="d7ddc-113">Output : 'T[][]</span></span>

<span data-ttu-id="d7ddc-114">Dönüştürülmüş $c \times r $ matrisi</span><span class="sxs-lookup"><span data-stu-id="d7ddc-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d7ddc-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="d7ddc-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d7ddc-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="d7ddc-116">'T</span></span>

<span data-ttu-id="d7ddc-117">Her öğesinin türü `matrix` .</span><span class="sxs-lookup"><span data-stu-id="d7ddc-117">The type of each element of `matrix`.</span></span>