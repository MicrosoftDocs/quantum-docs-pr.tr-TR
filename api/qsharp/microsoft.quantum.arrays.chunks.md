---
uid: Microsoft.Quantum.Arrays.Chunks
title: Öbekleri işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730415"
---
# <a name="chunks-function"></a><span data-ttu-id="10a51-102">Öbekleri işlevi</span><span class="sxs-lookup"><span data-stu-id="10a51-102">Chunks function</span></span>

<span data-ttu-id="10a51-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="10a51-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="10a51-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="10a51-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="10a51-105">Bir diziyi eşit uzunlukta birden çok parçaya böler.</span><span class="sxs-lookup"><span data-stu-id="10a51-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="10a51-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="10a51-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="10a51-107">nElements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="10a51-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="10a51-108">Her bir öbekin uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="10a51-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="10a51-109">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="10a51-109">arr : 'T[]</span></span>

<span data-ttu-id="10a51-110">Bölünecek dizi.</span><span class="sxs-lookup"><span data-stu-id="10a51-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="10a51-111">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="10a51-111">Output : 'T[][]</span></span>

<span data-ttu-id="10a51-112">Özgün dizinin her öbeğini içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="10a51-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="10a51-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="10a51-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="10a51-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="10a51-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="10a51-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="10a51-115">Remarks</span></span>

<span data-ttu-id="10a51-116">Çıktının son öğesi `nElements` `Length(arr)` tarafından bölünemediğinden daha kısa olabileceğini unutmayın `nElements` .</span><span class="sxs-lookup"><span data-stu-id="10a51-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>