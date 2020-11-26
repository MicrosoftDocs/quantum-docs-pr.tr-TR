---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 24606486b3d5703065a7c7f62d3bbc7e3d07615f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205414"
---
# <a name="repeatca-operation"></a><span data-ttu-id="a510e-102">RepeatCA işlemi</span><span class="sxs-lookup"><span data-stu-id="a510e-102">RepeatCA operation</span></span>

<span data-ttu-id="a510e-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a510e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a510e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a510e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a510e-105">Bir işlemi verilen sayıda yineler.</span><span class="sxs-lookup"><span data-stu-id="a510e-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a510e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a510e-106">Input</span></span>

### <a name="op--tinput--unit--is-adj--ctl"></a><span data-ttu-id="a510e-107">Op: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  , ayarlanabilir ve CTL</span><span class="sxs-lookup"><span data-stu-id="a510e-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a510e-108">İşlemin tekrar çağrılması.</span><span class="sxs-lookup"><span data-stu-id="a510e-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="a510e-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a510e-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a510e-110">Çağrılacak zaman sayısı `op` .</span><span class="sxs-lookup"><span data-stu-id="a510e-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="a510e-111">Giriş: ' TInput</span><span class="sxs-lookup"><span data-stu-id="a510e-111">input : 'TInput</span></span>

<span data-ttu-id="a510e-112">Geçirilecek giriş `op` .</span><span class="sxs-lookup"><span data-stu-id="a510e-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a510e-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a510e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a510e-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="a510e-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="a510e-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="a510e-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="a510e-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a510e-116">See Also</span></span>

- [<span data-ttu-id="a510e-117">Microsoft. hisse. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="a510e-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="a510e-118">Microsoft. hisse. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="a510e-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="a510e-119">Microsoft. hisse. Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="a510e-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="a510e-120">Microsoft. hisse. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="a510e-120">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)