---
uid: Microsoft.Quantum.Canon.ConjugatedByC
title: Birleşik Gatedbyc işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByC
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 1aa471a0f9039151d130bd52a026f4c1a0765e32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216685"
---
# <a name="conjugatedbyc-function"></a><span data-ttu-id="bd8ab-102">Birleşik Gatedbyc işlevi</span><span class="sxs-lookup"><span data-stu-id="bd8ab-102">ConjugatedByC function</span></span>

<span data-ttu-id="bd8ab-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bd8ab-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bd8ab-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd8ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd8ab-105">Verilen dış ve iç işlemler, dış işlemin iç işlemini sağlayan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="bd8ab-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl)) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="bd8ab-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="bd8ab-106">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="bd8ab-107">outerOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="bd8ab-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="bd8ab-108">$V $ eşleniği için kullanılması gereken $U $ işlemi.</span><span class="sxs-lookup"><span data-stu-id="bd8ab-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="bd8ab-109">$U $ dış işleminin adjointable olması gerektiğini, ancak denetlenebilir olması gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="bd8ab-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-ctl"></a><span data-ttu-id="bd8ab-110">ınneroperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="bd8ab-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="bd8ab-111">İşlem $V $.</span><span class="sxs-lookup"><span data-stu-id="bd8ab-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="bd8ab-112">Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="bd8ab-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="bd8ab-113">Eylemi Unitary $U ^ {\hanger} V U $ tarafından temsil edilen yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="bd8ab-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bd8ab-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="bd8ab-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bd8ab-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="bd8ab-115">'T</span></span>

<span data-ttu-id="bd8ab-116">Her iç ve dış işlemin işlem yapması için gereken hedefin türü.</span><span class="sxs-lookup"><span data-stu-id="bd8ab-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd8ab-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bd8ab-117">Remarks</span></span>

<span data-ttu-id="bd8ab-118">Dış işlemin her zaman adjointable olduğu varsayılır, ancak birleştirilmiş işlemin denetlenebilir olması için denetlenebilir olması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="bd8ab-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd8ab-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bd8ab-119">See Also</span></span>

- [<span data-ttu-id="bd8ab-120">Microsoft. hisse. Canon. Birleşik Gatedby</span><span class="sxs-lookup"><span data-stu-id="bd8ab-120">Microsoft.Quantum.Canon.ConjugatedBy</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedBy)
- [<span data-ttu-id="bd8ab-121">Microsoft. hisse. Canon. Birleşik Gatedbya</span><span class="sxs-lookup"><span data-stu-id="bd8ab-121">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="bd8ab-122">Microsoft. hisse. Canon. Birleşik Gatedbyca</span><span class="sxs-lookup"><span data-stu-id="bd8ab-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="bd8ab-123">Microsoft. hisse. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="bd8ab-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)