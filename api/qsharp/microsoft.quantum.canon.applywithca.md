---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: ApplyWithCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: abc62791416e78c1b2937a226327b71da8b8e288
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729006"
---
# <a name="applywithca-operation"></a><span data-ttu-id="e7d2f-102">ApplyWithCA işlemi</span><span class="sxs-lookup"><span data-stu-id="e7d2f-102">ApplyWithCA operation</span></span>

<span data-ttu-id="e7d2f-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e7d2f-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e7d2f-105">İki işlem verildiğinde, diğerini diğeri ile birlikte uygular.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="e7d2f-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e7d2f-106">Description</span></span>

<span data-ttu-id="e7d2f-107">Sırasıyla Unitary işleçleri $U $ ve $V $ tarafından tanımlanan iki işlem, bu dosyaları ^ {\abger} V U $ $U dizisine uygular.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="e7d2f-108">Diğer bir deyişle, bu işlem $U $ ile $V $ Birleşik tarafından verilen Unitary işlecini uygular.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="e7d2f-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="e7d2f-109">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="e7d2f-110">outerOperation: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="e7d2f-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="e7d2f-111">$V $ eşleniği için kullanılması gereken $U $ işlemi.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="e7d2f-112">$U $ dış işleminin adjointable olması gerektiğini, ancak denetlenebilir olması gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-adj--ctl"></a><span data-ttu-id="e7d2f-113">ınneroperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="e7d2f-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="e7d2f-114">İşlem $V $.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="e7d2f-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="e7d2f-115">target : 'T</span></span>

<span data-ttu-id="e7d2f-116">Dış ve iç işlemlere sağlanacak giriş.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e7d2f-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e7d2f-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e7d2f-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e7d2f-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e7d2f-119">'T</span></span>

<span data-ttu-id="e7d2f-120">Her iç ve dış işlemin üzerinde işlem gören hedef.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7d2f-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e7d2f-121">Remarks</span></span>

<span data-ttu-id="e7d2f-122">Dış işlemin her zaman adjointable olduğu varsayılır, ancak birleştirilmiş işlemin denetlenebilir olması için denetlenebilir olması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7d2f-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-123">See Also</span></span>

- [<span data-ttu-id="e7d2f-124">Microsoft. hisse. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="e7d2f-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="e7d2f-125">Microsoft. hisse. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="e7d2f-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="e7d2f-126">Microsoft. hisse. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="e7d2f-126">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)