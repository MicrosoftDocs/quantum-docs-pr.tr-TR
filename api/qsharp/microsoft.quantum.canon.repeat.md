---
uid: Microsoft.Quantum.Canon.Repeat
title: İşlemi yinele
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: cd572e5e082df94d762a0869ad2c1923fb71fd3d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205618"
---
# <a name="repeat-operation"></a><span data-ttu-id="647ae-102">İşlemi yinele</span><span class="sxs-lookup"><span data-stu-id="647ae-102">Repeat operation</span></span>

<span data-ttu-id="647ae-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="647ae-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="647ae-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="647ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="647ae-105">Bir işlemi verilen sayıda yineler.</span><span class="sxs-lookup"><span data-stu-id="647ae-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="647ae-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="647ae-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="647ae-107">Op: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="647ae-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="647ae-108">İşlemin tekrar çağrılması.</span><span class="sxs-lookup"><span data-stu-id="647ae-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="647ae-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="647ae-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="647ae-110">Çağrılacak zaman sayısı `op` .</span><span class="sxs-lookup"><span data-stu-id="647ae-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="647ae-111">Giriş: ' TInput</span><span class="sxs-lookup"><span data-stu-id="647ae-111">input : 'TInput</span></span>

<span data-ttu-id="647ae-112">Geçirilecek giriş `op` .</span><span class="sxs-lookup"><span data-stu-id="647ae-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="647ae-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="647ae-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="647ae-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="647ae-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="647ae-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="647ae-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="647ae-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="647ae-116">See Also</span></span>

- [<span data-ttu-id="647ae-117">Microsoft. hisse. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="647ae-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="647ae-118">Microsoft. hisse. Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="647ae-118">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="647ae-119">Microsoft. hisse. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="647ae-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="647ae-120">Microsoft. hisse. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="647ae-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)