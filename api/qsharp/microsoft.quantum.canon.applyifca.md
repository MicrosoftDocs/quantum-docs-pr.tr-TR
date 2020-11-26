---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b0ac469d6dea51951e0d9b2cfceb54253d4b4c5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209630"
---
# <a name="applyifca-operation"></a><span data-ttu-id="4fa37-102">ApplyIfCA işlemi</span><span class="sxs-lookup"><span data-stu-id="4fa37-102">ApplyIfCA operation</span></span>

<span data-ttu-id="4fa37-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4fa37-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4fa37-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4fa37-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4fa37-105">Klasik bir bit üzerinde bir Unitary işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="4fa37-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4fa37-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4fa37-106">Description</span></span>

<span data-ttu-id="4fa37-107">Bir işlem `op` ve bir bit değeri verildiğinde, `bit` if ise için geçerlidir `op` `target` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="4fa37-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="4fa37-108">Varsa, `false` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="4fa37-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="4fa37-109">Sonek, `CA` uygulanacak işlemin Unitary (denetlenebilir ve adjointable) olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="4fa37-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="4fa37-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="4fa37-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="4fa37-111">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="4fa37-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4fa37-112">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="4fa37-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="4fa37-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4fa37-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4fa37-114">Op 'ın uygulanıp uygulanmadığını denetleyen bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="4fa37-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="4fa37-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="4fa37-115">target : 'T</span></span>

<span data-ttu-id="4fa37-116">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="4fa37-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4fa37-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4fa37-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4fa37-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="4fa37-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4fa37-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="4fa37-119">'T</span></span>

<span data-ttu-id="4fa37-120">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="4fa37-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4fa37-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4fa37-121">See Also</span></span>

- [<span data-ttu-id="4fa37-122">Microsoft. hisse. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="4fa37-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="4fa37-123">Microsoft. hisse. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="4fa37-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="4fa37-124">Microsoft. hisse. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="4fa37-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)