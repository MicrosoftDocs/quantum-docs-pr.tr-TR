---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730351"
---
# <a name="drawmany-operation"></a><span data-ttu-id="7dd08-102">DrawMany işlemi</span><span class="sxs-lookup"><span data-stu-id="7dd08-102">DrawMany operation</span></span>

<span data-ttu-id="7dd08-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7dd08-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7dd08-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7dd08-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7dd08-105">Bir işlemi belirli sayıda örnek için yineler ve çıktılarını bir dizide toplar.</span><span class="sxs-lookup"><span data-stu-id="7dd08-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="7dd08-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7dd08-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="7dd08-107">Op: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="7dd08-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="7dd08-108">İşlemin tekrar çağrılması.</span><span class="sxs-lookup"><span data-stu-id="7dd08-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="7dd08-109">nSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7dd08-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7dd08-110">Toplanacak çağrı örnekleri sayısı `op` .</span><span class="sxs-lookup"><span data-stu-id="7dd08-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="7dd08-111">Giriş: ' TInput</span><span class="sxs-lookup"><span data-stu-id="7dd08-111">input : 'TInput</span></span>

<span data-ttu-id="7dd08-112">Geçirilecek giriş `op` .</span><span class="sxs-lookup"><span data-stu-id="7dd08-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="7dd08-113">Çıkış: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="7dd08-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7dd08-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="7dd08-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="7dd08-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="7dd08-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="7dd08-116">' TOutput</span><span class="sxs-lookup"><span data-stu-id="7dd08-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="7dd08-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7dd08-117">See Also</span></span>

- [<span data-ttu-id="7dd08-118">Microsoft. hisse. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="7dd08-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)