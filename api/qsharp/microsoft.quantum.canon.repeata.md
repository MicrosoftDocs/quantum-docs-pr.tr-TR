---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5f418f67d7265d4cb39b3636906c74d33d80f472
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205567"
---
# <a name="repeata-operation"></a><span data-ttu-id="d69da-102">RepeatA işlemi</span><span class="sxs-lookup"><span data-stu-id="d69da-102">RepeatA operation</span></span>

<span data-ttu-id="d69da-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d69da-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d69da-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d69da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d69da-105">Bir işlemi verilen sayıda yineler.</span><span class="sxs-lookup"><span data-stu-id="d69da-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="d69da-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d69da-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="d69da-107">Op: ' TInput => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="d69da-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d69da-108">İşlemin tekrar çağrılması.</span><span class="sxs-lookup"><span data-stu-id="d69da-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="d69da-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d69da-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d69da-110">Çağrılacak zaman sayısı `op` .</span><span class="sxs-lookup"><span data-stu-id="d69da-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="d69da-111">Giriş: ' TInput</span><span class="sxs-lookup"><span data-stu-id="d69da-111">input : 'TInput</span></span>

<span data-ttu-id="d69da-112">Geçirilecek giriş `op` .</span><span class="sxs-lookup"><span data-stu-id="d69da-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d69da-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d69da-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d69da-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="d69da-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="d69da-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="d69da-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="d69da-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d69da-116">See Also</span></span>

- [<span data-ttu-id="d69da-117">Microsoft. hisse. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="d69da-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="d69da-118">Microsoft. hisse. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="d69da-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="d69da-119">Microsoft. hisse. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="d69da-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="d69da-120">Microsoft. hisse. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="d69da-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)