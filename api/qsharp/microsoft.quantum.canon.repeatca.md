---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: b68c3aa4298fffa76f7c43ac4c6d27cdf3b72fbf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728435"
---
# <a name="repeatca-operation"></a><span data-ttu-id="0840d-102">RepeatCA işlemi</span><span class="sxs-lookup"><span data-stu-id="0840d-102">RepeatCA operation</span></span>

<span data-ttu-id="0840d-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0840d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0840d-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0840d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0840d-105">Bir işlemi verilen sayıda yineler.</span><span class="sxs-lookup"><span data-stu-id="0840d-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="0840d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0840d-106">Input</span></span>

### <a name="op--tinput--unit-adj--ctl"></a><span data-ttu-id="0840d-107">Op: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="0840d-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0840d-108">İşlemin tekrar çağrılması.</span><span class="sxs-lookup"><span data-stu-id="0840d-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="0840d-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0840d-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0840d-110">Çağrılacak zaman sayısı `op` .</span><span class="sxs-lookup"><span data-stu-id="0840d-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="0840d-111">Giriş: ' TInput</span><span class="sxs-lookup"><span data-stu-id="0840d-111">input : 'TInput</span></span>

<span data-ttu-id="0840d-112">Geçirilecek giriş `op` .</span><span class="sxs-lookup"><span data-stu-id="0840d-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0840d-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0840d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0840d-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="0840d-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="0840d-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="0840d-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="0840d-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0840d-116">See Also</span></span>

- [<span data-ttu-id="0840d-117">Microsoft. hisse. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="0840d-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="0840d-118">Microsoft. hisse. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="0840d-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="0840d-119">Microsoft. hisse. Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="0840d-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="0840d-120">Microsoft. hisse. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="0840d-120">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)