---
uid: Microsoft.Quantum.Canon.Repeat
title: İşlemi yinele
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 40ee191e8d9044f33aa1621303c70f7e0847e8f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852238"
---
# <a name="repeat-operation"></a><span data-ttu-id="63045-102">İşlemi yinele</span><span class="sxs-lookup"><span data-stu-id="63045-102">Repeat operation</span></span>

<span data-ttu-id="63045-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="63045-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="63045-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63045-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63045-105">Bir işlemi verilen sayıda yineler.</span><span class="sxs-lookup"><span data-stu-id="63045-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="63045-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="63045-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="63045-107">Op: ' TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63045-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="63045-108">İşlemin tekrar çağrılması.</span><span class="sxs-lookup"><span data-stu-id="63045-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="63045-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="63045-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="63045-110">Çağrılacak zaman sayısı `op` .</span><span class="sxs-lookup"><span data-stu-id="63045-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="63045-111">Giriş: ' TInput</span><span class="sxs-lookup"><span data-stu-id="63045-111">input : 'TInput</span></span>

<span data-ttu-id="63045-112">Geçirilecek giriş `op` .</span><span class="sxs-lookup"><span data-stu-id="63045-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63045-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63045-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="63045-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="63045-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="63045-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="63045-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="63045-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="63045-116">Example</span></span>

<span data-ttu-id="63045-117">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="63045-117">The following are equivalent:</span></span>

```qsharp
Repeat(U, 17, target);
(Bound(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="63045-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="63045-118">See Also</span></span>

- [<span data-ttu-id="63045-119">Microsoft. hisse. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="63045-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="63045-120">Microsoft. hisse. Canon. RepeatA</span><span class="sxs-lookup"><span data-stu-id="63045-120">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="63045-121">Microsoft. hisse. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="63045-121">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="63045-122">Microsoft. hisse. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="63045-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)