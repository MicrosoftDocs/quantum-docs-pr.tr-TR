---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: ApplyWithCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: e86c452e9693c5a4d0d4e5a36471ab46bbf66dfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208151"
---
# <a name="applywithca-operation"></a><span data-ttu-id="c8938-102">ApplyWithCA işlemi</span><span class="sxs-lookup"><span data-stu-id="c8938-102">ApplyWithCA operation</span></span>

<span data-ttu-id="c8938-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c8938-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c8938-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8938-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8938-105">İki işlem verildiğinde, diğerini diğeri ile birlikte uygular.</span><span class="sxs-lookup"><span data-stu-id="c8938-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c8938-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c8938-106">Description</span></span>

<span data-ttu-id="c8938-107">Sırasıyla Unitary işleçleri $U $ ve $V $ tarafından tanımlanan iki işlem, bu dosyaları ^ {\abger} V U $ $U dizisine uygular.</span><span class="sxs-lookup"><span data-stu-id="c8938-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="c8938-108">Diğer bir deyişle, bu işlem $U $ ile $V $ Birleşik tarafından verilen Unitary işlecini uygular.</span><span class="sxs-lookup"><span data-stu-id="c8938-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="c8938-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="c8938-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="c8938-110">outerOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="c8938-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c8938-111">$V $ eşleniği için kullanılması gereken $U $ işlemi.</span><span class="sxs-lookup"><span data-stu-id="c8938-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="c8938-112">$U $ dış işleminin adjointable olması gerektiğini, ancak denetlenebilir olması gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="c8938-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj--ctl"></a><span data-ttu-id="c8938-113">ınneroperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="c8938-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c8938-114">İşlem $V $.</span><span class="sxs-lookup"><span data-stu-id="c8938-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="c8938-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="c8938-115">target : 'T</span></span>

<span data-ttu-id="c8938-116">Dış ve iç işlemlere sağlanacak giriş.</span><span class="sxs-lookup"><span data-stu-id="c8938-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c8938-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8938-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c8938-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c8938-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c8938-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c8938-119">'T</span></span>

<span data-ttu-id="c8938-120">Her iç ve dış işlemin üzerinde işlem gören hedef.</span><span class="sxs-lookup"><span data-stu-id="c8938-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8938-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c8938-121">Remarks</span></span>

<span data-ttu-id="c8938-122">Dış işlemin her zaman adjointable olduğu varsayılır, ancak birleştirilmiş işlemin denetlenebilir olması için denetlenebilir olması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="c8938-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8938-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c8938-123">See Also</span></span>

- [<span data-ttu-id="c8938-124">Microsoft. hisse. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="c8938-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="c8938-125">Microsoft. hisse. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="c8938-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="c8938-126">Microsoft. hisse. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="c8938-126">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)