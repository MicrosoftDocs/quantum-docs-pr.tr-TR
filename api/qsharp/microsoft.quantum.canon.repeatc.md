---
uid: Microsoft.Quantum.Canon.RepeatC
title: RepeatC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 30fd172584b36601c4b81deff494cf55964518f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205448"
---
# <a name="repeatc-operation"></a><span data-ttu-id="f97b2-102">RepeatC işlemi</span><span class="sxs-lookup"><span data-stu-id="f97b2-102">RepeatC operation</span></span>

<span data-ttu-id="f97b2-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f97b2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f97b2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f97b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f97b2-105">Bir işlemi verilen sayıda yineler.</span><span class="sxs-lookup"><span data-stu-id="f97b2-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="f97b2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f97b2-106">Input</span></span>

### <a name="op--tinput--unit--is-ctl"></a><span data-ttu-id="f97b2-107">Op: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="f97b2-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f97b2-108">İşlemin tekrar çağrılması.</span><span class="sxs-lookup"><span data-stu-id="f97b2-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="f97b2-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f97b2-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f97b2-110">Çağrılacak zaman sayısı `op` .</span><span class="sxs-lookup"><span data-stu-id="f97b2-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="f97b2-111">Giriş: ' TInput</span><span class="sxs-lookup"><span data-stu-id="f97b2-111">input : 'TInput</span></span>

<span data-ttu-id="f97b2-112">Geçirilecek giriş `op` .</span><span class="sxs-lookup"><span data-stu-id="f97b2-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f97b2-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f97b2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f97b2-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f97b2-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="f97b2-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="f97b2-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="f97b2-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f97b2-116">See Also</span></span>

- [<span data-ttu-id="f97b2-117">Microsoft. hisse. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="f97b2-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="f97b2-118">Microsoft. hisse. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="f97b2-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="f97b2-119">Microsoft. hisse. Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="f97b2-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="f97b2-120">Microsoft. hisse. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="f97b2-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)