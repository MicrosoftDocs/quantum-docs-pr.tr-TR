---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: ApplyWithC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 172f9098a53c97e71f160b4a48479c3184be4385
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217246"
---
# <a name="applywithc-operation"></a><span data-ttu-id="85e4d-102">ApplyWithC işlemi</span><span class="sxs-lookup"><span data-stu-id="85e4d-102">ApplyWithC operation</span></span>

<span data-ttu-id="85e4d-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="85e4d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="85e4d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85e4d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85e4d-105">İki işlem verildiğinde, diğerini diğeri ile birlikte uygular.</span><span class="sxs-lookup"><span data-stu-id="85e4d-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="85e4d-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="85e4d-106">Description</span></span>

<span data-ttu-id="85e4d-107">Sırasıyla Unitary işleçleri $U $ ve $V $ tarafından tanımlanan iki işlem, bu dosyaları ^ {\abger} V U $ $U dizisine uygular.</span><span class="sxs-lookup"><span data-stu-id="85e4d-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="85e4d-108">Diğer bir deyişle, bu işlem $U $ ile $V $ Birleşik tarafından verilen Unitary işlecini uygular.</span><span class="sxs-lookup"><span data-stu-id="85e4d-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="85e4d-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="85e4d-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="85e4d-110">outerOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="85e4d-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="85e4d-111">$V $ eşleniği için kullanılması gereken $U $ işlemi.</span><span class="sxs-lookup"><span data-stu-id="85e4d-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="85e4d-112">$U $ dış işleminin adjointable olması gerektiğini, ancak denetlenebilir olması gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="85e4d-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-ctl"></a><span data-ttu-id="85e4d-113">ınneroperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="85e4d-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="85e4d-114">İşlem $V $.</span><span class="sxs-lookup"><span data-stu-id="85e4d-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="85e4d-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="85e4d-115">target : 'T</span></span>

<span data-ttu-id="85e4d-116">Dış ve iç işlemlere sağlanacak giriş.</span><span class="sxs-lookup"><span data-stu-id="85e4d-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="85e4d-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="85e4d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="85e4d-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="85e4d-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="85e4d-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="85e4d-119">'T</span></span>

<span data-ttu-id="85e4d-120">Her iç ve dış işlemin üzerinde işlem gören hedef.</span><span class="sxs-lookup"><span data-stu-id="85e4d-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="85e4d-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="85e4d-121">Remarks</span></span>

<span data-ttu-id="85e4d-122">Dış işlemin her zaman adjointable olduğu varsayılır, ancak birleştirilmiş işlemin denetlenebilir olması için denetlenebilir olması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="85e4d-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="85e4d-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="85e4d-123">See Also</span></span>

- [<span data-ttu-id="85e4d-124">Microsoft. hisse. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="85e4d-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="85e4d-125">Microsoft. hisse. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="85e4d-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="85e4d-126">Microsoft. hisse. Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="85e4d-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)