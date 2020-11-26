---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210004"
---
# <a name="drawmany-operation"></a><span data-ttu-id="ead77-102">DrawMany işlemi</span><span class="sxs-lookup"><span data-stu-id="ead77-102">DrawMany operation</span></span>

<span data-ttu-id="ead77-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ead77-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ead77-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ead77-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ead77-105">Bir işlemi belirli sayıda örnek için yineler ve çıktılarını bir dizide toplar.</span><span class="sxs-lookup"><span data-stu-id="ead77-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="ead77-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ead77-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="ead77-107">Op: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="ead77-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="ead77-108">İşlemin tekrar çağrılması.</span><span class="sxs-lookup"><span data-stu-id="ead77-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="ead77-109">nSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ead77-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ead77-110">Toplanacak çağrı örnekleri sayısı `op` .</span><span class="sxs-lookup"><span data-stu-id="ead77-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="ead77-111">Giriş: ' TInput</span><span class="sxs-lookup"><span data-stu-id="ead77-111">input : 'TInput</span></span>

<span data-ttu-id="ead77-112">Geçirilecek giriş `op` .</span><span class="sxs-lookup"><span data-stu-id="ead77-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="ead77-113">Çıkış: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="ead77-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ead77-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ead77-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="ead77-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="ead77-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="ead77-116">' TOutput</span><span class="sxs-lookup"><span data-stu-id="ead77-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="ead77-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ead77-117">See Also</span></span>

- [<span data-ttu-id="ead77-118">Microsoft. hisse. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="ead77-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)