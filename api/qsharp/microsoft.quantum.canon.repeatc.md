---
uid: Microsoft.Quantum.Canon.RepeatC
title: RepeatC işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 8dc178374bdc9f8bf9f8aed57b9ae9a56995dec6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728436"
---
# <a name="repeatc-operation"></a><span data-ttu-id="3bb29-102">RepeatC işlemi</span><span class="sxs-lookup"><span data-stu-id="3bb29-102">RepeatC operation</span></span>

<span data-ttu-id="3bb29-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3bb29-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3bb29-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3bb29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3bb29-105">Bir işlemi verilen sayıda yineler.</span><span class="sxs-lookup"><span data-stu-id="3bb29-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="3bb29-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3bb29-106">Input</span></span>

### <a name="op--tinput--unit-ctl"></a><span data-ttu-id="3bb29-107">Op: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="3bb29-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="3bb29-108">İşlemin tekrar çağrılması.</span><span class="sxs-lookup"><span data-stu-id="3bb29-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="3bb29-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3bb29-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3bb29-110">Çağrılacak zaman sayısı `op` .</span><span class="sxs-lookup"><span data-stu-id="3bb29-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="3bb29-111">Giriş: ' TInput</span><span class="sxs-lookup"><span data-stu-id="3bb29-111">input : 'TInput</span></span>

<span data-ttu-id="3bb29-112">Geçirilecek giriş `op` .</span><span class="sxs-lookup"><span data-stu-id="3bb29-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3bb29-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3bb29-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3bb29-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="3bb29-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="3bb29-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="3bb29-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="3bb29-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3bb29-116">See Also</span></span>

- [<span data-ttu-id="3bb29-117">Microsoft. hisse. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="3bb29-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="3bb29-118">Microsoft. hisse. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="3bb29-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="3bb29-119">Microsoft. hisse. Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="3bb29-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="3bb29-120">Microsoft. hisse. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="3bb29-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)