---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: Birleşik Gatedbyca işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: df29bcf555026bceb13d6896db12e13671a49b9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728820"
---
# <a name="conjugatedbyca-function"></a><span data-ttu-id="273e1-102">Birleşik Gatedbyca işlevi</span><span class="sxs-lookup"><span data-stu-id="273e1-102">ConjugatedByCA function</span></span>

<span data-ttu-id="273e1-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="273e1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="273e1-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="273e1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="273e1-105">Verilen dış ve iç işlemler, dış işlemin iç işlemini sağlayan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="273e1-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="273e1-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="273e1-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="273e1-107">outerOperation: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="273e1-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="273e1-108">$V $ eşleniği için kullanılması gereken $U $ işlemi.</span><span class="sxs-lookup"><span data-stu-id="273e1-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="273e1-109">$U $ dış işleminin adjointable olması gerektiğini, ancak denetlenebilir olması gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="273e1-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-adj--ctl"></a><span data-ttu-id="273e1-110">ınneroperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="273e1-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="273e1-111">İşlem $V $.</span><span class="sxs-lookup"><span data-stu-id="273e1-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="273e1-112">Çıkış: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="273e1-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="273e1-113">Eylemi Unitary $U ^ {\hanger} V U $ tarafından temsil edilen yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="273e1-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="273e1-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="273e1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="273e1-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="273e1-115">'T</span></span>

<span data-ttu-id="273e1-116">Her iç ve dış işlemin işlem yapması için gereken hedefin türü.</span><span class="sxs-lookup"><span data-stu-id="273e1-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="273e1-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="273e1-117">Remarks</span></span>

<span data-ttu-id="273e1-118">Dış işlemin her zaman adjointable olduğu varsayılır, ancak birleştirilmiş işlemin denetlenebilir olması için denetlenebilir olması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="273e1-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="273e1-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="273e1-119">See Also</span></span>

- [<span data-ttu-id="273e1-120">Microsoft. hisse. Canon. Birleşik Gatedbya</span><span class="sxs-lookup"><span data-stu-id="273e1-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="273e1-121">Microsoft. hisse. Canon. Birleşik Gatedbyc</span><span class="sxs-lookup"><span data-stu-id="273e1-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="273e1-122">Microsoft. hisse. Canon. Birleşik Gatedbyca</span><span class="sxs-lookup"><span data-stu-id="273e1-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="273e1-123">Microsoft. hisse. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="273e1-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)