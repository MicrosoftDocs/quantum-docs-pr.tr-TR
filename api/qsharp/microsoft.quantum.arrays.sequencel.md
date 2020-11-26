---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220272"
---
# <a name="sequencel-function"></a><span data-ttu-id="93959-102">SequenceL işlevi</span><span class="sxs-lookup"><span data-stu-id="93959-102">SequenceL function</span></span>

<span data-ttu-id="93959-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="93959-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="93959-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93959-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93959-105">Verilen bir aralıktaki tamsayıların dizisini alır.</span><span class="sxs-lookup"><span data-stu-id="93959-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="93959-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="93959-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="93959-107">Kimden: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="93959-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="93959-108">Aralığın kapsamlı başlangıç dizini.</span><span class="sxs-lookup"><span data-stu-id="93959-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="93959-109">Şu şekilde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="93959-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="93959-110">Aralıktan küçük olmayan aralığın kapsamlı bir bitiş dizini `from` .</span><span class="sxs-lookup"><span data-stu-id="93959-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="93959-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="93959-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="93959-112">Sayı dizisini içeren bir dizi `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="93959-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="93959-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="93959-113">Remarks</span></span>

<span data-ttu-id="93959-114">Ve arasındaki fark `from` `to` bir değere sığması gerekir `Int` .</span><span class="sxs-lookup"><span data-stu-id="93959-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>