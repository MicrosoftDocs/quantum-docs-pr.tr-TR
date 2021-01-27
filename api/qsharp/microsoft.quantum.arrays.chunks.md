---
uid: Microsoft.Quantum.Arrays.Chunks
title: Öbekleri işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842884"
---
# <a name="chunks-function"></a><span data-ttu-id="c9433-102">Öbekleri işlevi</span><span class="sxs-lookup"><span data-stu-id="c9433-102">Chunks function</span></span>

<span data-ttu-id="c9433-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c9433-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c9433-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9433-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9433-105">Bir diziyi eşit uzunlukta birden çok parçaya böler.</span><span class="sxs-lookup"><span data-stu-id="c9433-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="c9433-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c9433-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="c9433-107">nElements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9433-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c9433-108">Her bir öbekin uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="c9433-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="c9433-109">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="c9433-109">arr : 'T[]</span></span>

<span data-ttu-id="c9433-110">Bölünecek dizi.</span><span class="sxs-lookup"><span data-stu-id="c9433-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="c9433-111">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="c9433-111">Output : 'T[][]</span></span>

<span data-ttu-id="c9433-112">Özgün dizinin her öbeğini içeren bir dizi.</span><span class="sxs-lookup"><span data-stu-id="c9433-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c9433-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c9433-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c9433-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c9433-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="c9433-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c9433-115">Remarks</span></span>

<span data-ttu-id="c9433-116">Çıktının son öğesi `nElements` `Length(arr)` tarafından bölünemediğinden daha kısa olabileceğini unutmayın `nElements` .</span><span class="sxs-lookup"><span data-stu-id="c9433-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>