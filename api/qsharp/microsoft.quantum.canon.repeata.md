---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 9ae3123a64b2a886df3b7575b2840522f9b011ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852233"
---
# <a name="repeata-operation"></a><span data-ttu-id="eee34-102">RepeatA işlemi</span><span class="sxs-lookup"><span data-stu-id="eee34-102">RepeatA operation</span></span>

<span data-ttu-id="eee34-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eee34-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eee34-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eee34-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eee34-105">Bir işlemi verilen sayıda yineler.</span><span class="sxs-lookup"><span data-stu-id="eee34-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="eee34-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="eee34-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="eee34-107">Op: ' TInput => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="eee34-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="eee34-108">İşlemin tekrar çağrılması.</span><span class="sxs-lookup"><span data-stu-id="eee34-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="eee34-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eee34-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eee34-110">Çağrılacak zaman sayısı `op` .</span><span class="sxs-lookup"><span data-stu-id="eee34-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="eee34-111">Giriş: ' TInput</span><span class="sxs-lookup"><span data-stu-id="eee34-111">input : 'TInput</span></span>

<span data-ttu-id="eee34-112">Geçirilecek giriş `op` .</span><span class="sxs-lookup"><span data-stu-id="eee34-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eee34-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eee34-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eee34-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="eee34-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="eee34-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="eee34-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="eee34-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="eee34-116">Example</span></span>

<span data-ttu-id="eee34-117">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="eee34-117">The following are equivalent:</span></span>

```qsharp
RepeatA(U, 17, target);
(BoundA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="eee34-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="eee34-118">See Also</span></span>

- [<span data-ttu-id="eee34-119">Microsoft. hisse. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="eee34-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="eee34-120">Microsoft. hisse. Canon. Repeat</span><span class="sxs-lookup"><span data-stu-id="eee34-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="eee34-121">Microsoft. hisse. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="eee34-121">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="eee34-122">Microsoft. hisse. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="eee34-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)