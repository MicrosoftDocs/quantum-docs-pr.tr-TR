---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: ApplyIfElseBC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: ea06b0a0a07659407e13caa2baa4f3e37ca2a0f7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209528"
---
# <a name="applyifelsebc-operation"></a><span data-ttu-id="8ec76-102">ApplyIfElseBC işlemi</span><span class="sxs-lookup"><span data-stu-id="8ec76-102">ApplyIfElseBC operation</span></span>

<span data-ttu-id="8ec76-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8ec76-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8ec76-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ec76-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ec76-105">Klasik bir bitin değerine bağlı olarak, iki denetlenebilir işlemden birini uygular.</span><span class="sxs-lookup"><span data-stu-id="8ec76-105">Applies one of two controllable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="8ec76-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="8ec76-106">Description</span></span>

<span data-ttu-id="8ec76-107">Bir bit verildiğinde, `bit` `trueOp` `trueInput` ,, olduğu zaman girişi olarak ile işlemini `bit` uygular `true` ve `falseOp(falseInput)` ne zaman geçerlidir `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="8ec76-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="8ec76-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="8ec76-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="8ec76-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8ec76-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8ec76-110">`trueOp`Veya uygulanıp uygulanmadığını belirlemede kullanılan Boolean değeri `falseOp` .</span><span class="sxs-lookup"><span data-stu-id="8ec76-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-ctl"></a><span data-ttu-id="8ec76-111">trueOp: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="8ec76-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8ec76-112">Olduğunda uygulanacak denetlenebilir işlem `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="8ec76-112">The controllable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="8ec76-113">Trueınput: 'T</span><span class="sxs-lookup"><span data-stu-id="8ec76-113">trueInput : 'T</span></span>

<span data-ttu-id="8ec76-114">Olduğunda olarak sağlanacak giriş `trueOp` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="8ec76-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-ctl"></a><span data-ttu-id="8ec76-115">Yanlışop: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="8ec76-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8ec76-116">Olduğunda uygulanacak denetlenebilir işlem `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="8ec76-116">The controllable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="8ec76-117">Yanlışgiriş: ' U</span><span class="sxs-lookup"><span data-stu-id="8ec76-117">falseInput : 'U</span></span>

<span data-ttu-id="8ec76-118">Olduğunda olarak sağlanacak giriş `falseOp` `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="8ec76-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ec76-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ec76-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8ec76-120">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="8ec76-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8ec76-121">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="8ec76-121">'T</span></span>

<span data-ttu-id="8ec76-122">Koşullu olarak uygulanacak işlemin giriş türü `trueOp` .</span><span class="sxs-lookup"><span data-stu-id="8ec76-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="8ec76-123">' U</span><span class="sxs-lookup"><span data-stu-id="8ec76-123">'U</span></span>

<span data-ttu-id="8ec76-124">Koşullu olarak uygulanacak işlemin giriş türü `falseOp` .</span><span class="sxs-lookup"><span data-stu-id="8ec76-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ec76-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8ec76-125">See Also</span></span>

- [<span data-ttu-id="8ec76-126">Microsoft. hisse. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="8ec76-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="8ec76-127">Microsoft. hisse. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="8ec76-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="8ec76-128">Microsoft. hisse. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="8ec76-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="8ec76-129">Microsoft. hisse. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="8ec76-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="8ec76-130">Microsoft. hisse. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="8ec76-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)