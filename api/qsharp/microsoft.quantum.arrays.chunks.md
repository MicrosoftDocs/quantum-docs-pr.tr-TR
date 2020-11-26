---
uid: Microsoft.Quantum.Arrays.Chunks
title: Öbekleri işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221615"
---
# <a name="chunks-function"></a><span data-ttu-id="a34c0-102">Öbekleri işlevi</span><span class="sxs-lookup"><span data-stu-id="a34c0-102">Chunks function</span></span>

<span data-ttu-id="a34c0-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a34c0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a34c0-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a34c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a34c0-105">Bir diziyi eşit uzunlukta birden çok parçaya böler.</span><span class="sxs-lookup"><span data-stu-id="a34c0-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="a34c0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a34c0-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="a34c0-107">nElements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a34c0-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a34c0-108">Her bir öbekin uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="a34c0-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="a34c0-109">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="a34c0-109">arr : 'T[]</span></span>

<span data-ttu-id="a34c0-110">Bölünecek dizi.</span><span class="sxs-lookup"><span data-stu-id="a34c0-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="a34c0-111">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="a34c0-111">Output : 'T[][]</span></span>

<span data-ttu-id="a34c0-112">Özgün dizinin her öbeğini içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="a34c0-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a34c0-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="a34c0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a34c0-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="a34c0-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="a34c0-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a34c0-115">Remarks</span></span>

<span data-ttu-id="a34c0-116">Çıktının son öğesi `nElements` `Length(arr)` tarafından bölünemediğinden daha kısa olabileceğini unutmayın `nElements` .</span><span class="sxs-lookup"><span data-stu-id="a34c0-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>