---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846216"
---
# <a name="drawmany-operation"></a><span data-ttu-id="06291-102">DrawMany işlemi</span><span class="sxs-lookup"><span data-stu-id="06291-102">DrawMany operation</span></span>

<span data-ttu-id="06291-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="06291-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="06291-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06291-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06291-105">Bir işlemi belirli sayıda örnek için yineler ve çıktılarını bir dizide toplar.</span><span class="sxs-lookup"><span data-stu-id="06291-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="06291-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="06291-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="06291-107">Op: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="06291-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="06291-108">İşlemin tekrar çağrılması.</span><span class="sxs-lookup"><span data-stu-id="06291-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="06291-109">nSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="06291-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="06291-110">Toplanacak çağrı örnekleri sayısı `op` .</span><span class="sxs-lookup"><span data-stu-id="06291-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="06291-111">Giriş: ' TInput</span><span class="sxs-lookup"><span data-stu-id="06291-111">input : 'TInput</span></span>

<span data-ttu-id="06291-112">Geçirilecek giriş `op` .</span><span class="sxs-lookup"><span data-stu-id="06291-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="06291-113">Çıkış: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="06291-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="06291-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="06291-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="06291-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="06291-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="06291-116">' TOutput</span><span class="sxs-lookup"><span data-stu-id="06291-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="06291-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="06291-117">Example</span></span>

<span data-ttu-id="06291-118">Aşağıdaki örnek, bir kerede tek bir bit örneklerindeki bir işlem verildiğinde bir tamsayıdır.</span><span class="sxs-lookup"><span data-stu-id="06291-118">The following samples an integer, given an operation that samples a single bit at a time.</span></span>

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a><span data-ttu-id="06291-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="06291-119">See Also</span></span>

- [<span data-ttu-id="06291-120">Microsoft. hisse. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="06291-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)