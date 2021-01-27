---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: af93220562d6be27b2f41e770bd953e5e808fcbf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852202"
---
# <a name="repeatca-operation"></a><span data-ttu-id="2fb6f-102">RepeatCA işlemi</span><span class="sxs-lookup"><span data-stu-id="2fb6f-102">RepeatCA operation</span></span>

<span data-ttu-id="2fb6f-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2fb6f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2fb6f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2fb6f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2fb6f-105">Bir işlemi verilen sayıda yineler.</span><span class="sxs-lookup"><span data-stu-id="2fb6f-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2fb6f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2fb6f-106">Input</span></span>

### <a name="op--tinput--unit--is-adj--ctl"></a><span data-ttu-id="2fb6f-107">Op: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  , ayarlanabilir ve CTL</span><span class="sxs-lookup"><span data-stu-id="2fb6f-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2fb6f-108">İşlemin tekrar çağrılması.</span><span class="sxs-lookup"><span data-stu-id="2fb6f-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="2fb6f-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2fb6f-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2fb6f-110">Çağrılacak zaman sayısı `op` .</span><span class="sxs-lookup"><span data-stu-id="2fb6f-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="2fb6f-111">Giriş: ' TInput</span><span class="sxs-lookup"><span data-stu-id="2fb6f-111">input : 'TInput</span></span>

<span data-ttu-id="2fb6f-112">Geçirilecek giriş `op` .</span><span class="sxs-lookup"><span data-stu-id="2fb6f-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2fb6f-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2fb6f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2fb6f-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2fb6f-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="2fb6f-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="2fb6f-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="2fb6f-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="2fb6f-116">Example</span></span>

<span data-ttu-id="2fb6f-117">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="2fb6f-117">The following are equivalent:</span></span>

```qsharp
RepeatCA(U, 17, target);
(BoundCA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="2fb6f-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2fb6f-118">See Also</span></span>

- [<span data-ttu-id="2fb6f-119">Microsoft. hisse. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="2fb6f-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="2fb6f-120">Microsoft. hisse. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="2fb6f-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="2fb6f-121">Microsoft. hisse. Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="2fb6f-121">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="2fb6f-122">Microsoft. hisse. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="2fb6f-122">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)