---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 89d34e5a30a61dee392904ce1076605432e21395
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728441"
---
# <a name="repeata-operation"></a><span data-ttu-id="592be-102">RepeatA işlemi</span><span class="sxs-lookup"><span data-stu-id="592be-102">RepeatA operation</span></span>

<span data-ttu-id="592be-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="592be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="592be-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="592be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="592be-105">Bir işlemi verilen sayıda yineler.</span><span class="sxs-lookup"><span data-stu-id="592be-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="592be-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="592be-106">Input</span></span>

### <a name="op--tinput--unit-adj"></a><span data-ttu-id="592be-107">Op: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="592be-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="592be-108">İşlemin tekrar çağrılması.</span><span class="sxs-lookup"><span data-stu-id="592be-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="592be-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="592be-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="592be-110">Çağrılacak zaman sayısı `op` .</span><span class="sxs-lookup"><span data-stu-id="592be-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="592be-111">Giriş: ' TInput</span><span class="sxs-lookup"><span data-stu-id="592be-111">input : 'TInput</span></span>

<span data-ttu-id="592be-112">Geçirilecek giriş `op` .</span><span class="sxs-lookup"><span data-stu-id="592be-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="592be-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="592be-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="592be-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="592be-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="592be-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="592be-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="592be-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="592be-116">See Also</span></span>

- [<span data-ttu-id="592be-117">Microsoft. hisse. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="592be-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="592be-118">Microsoft. hisse. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="592be-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="592be-119">Microsoft. hisse. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="592be-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="592be-120">Microsoft. hisse. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="592be-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)