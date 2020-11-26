---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: ApplyIfC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: 35430cb7cf491965b7b69ace6d3f41599dbadd51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218725"
---
# <a name="applyifc-operation"></a><span data-ttu-id="7644d-102">ApplyIfC işlemi</span><span class="sxs-lookup"><span data-stu-id="7644d-102">ApplyIfC operation</span></span>

<span data-ttu-id="7644d-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7644d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7644d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7644d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7644d-105">Klasik bir bit üzerinde bir denetlenebilir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="7644d-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="7644d-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7644d-106">Description</span></span>

<span data-ttu-id="7644d-107">Bir işlem `op` ve bir bit değeri verildiğinde, `bit` if ise için geçerlidir `op` `target` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="7644d-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="7644d-108">Varsa, `false` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="7644d-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="7644d-109">Sonek, `C` uygulanacak işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="7644d-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="7644d-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="7644d-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="7644d-111">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="7644d-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="7644d-112">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="7644d-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="7644d-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7644d-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7644d-114">Op 'ın uygulanıp uygulanmadığını denetleyen bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="7644d-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="7644d-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="7644d-115">target : 'T</span></span>

<span data-ttu-id="7644d-116">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="7644d-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7644d-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7644d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7644d-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="7644d-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7644d-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="7644d-119">'T</span></span>

<span data-ttu-id="7644d-120">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="7644d-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7644d-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7644d-121">See Also</span></span>

- [<span data-ttu-id="7644d-122">Microsoft. hisse. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="7644d-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="7644d-123">Microsoft. hisse. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="7644d-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="7644d-124">Microsoft. hisse. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="7644d-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)