---
uid: Microsoft.Quantum.Canon.ApplyIfElseB
title: ApplyIfElseB işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseB
qsharp.summary: Applies one of two operations, depending on the value of a classical bit.
ms.openlocfilehash: 68c06a5141b9ff423c2d18adc3a9e162eed939f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729583"
---
# <a name="applyifelseb-operation"></a><span data-ttu-id="bae58-102">ApplyIfElseB işlemi</span><span class="sxs-lookup"><span data-stu-id="bae58-102">ApplyIfElseB operation</span></span>

<span data-ttu-id="bae58-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bae58-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bae58-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bae58-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bae58-105">Klasik bitin değerine bağlı olarak iki işlemden birini uygular.</span><span class="sxs-lookup"><span data-stu-id="bae58-105">Applies one of two operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseB<'T, 'U> (bit : Bool, (trueOp : ('T => Unit), trueInput : 'T), (falseOp : ('U => Unit), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="bae58-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bae58-106">Description</span></span>

<span data-ttu-id="bae58-107">Bir bit verildiğinde, `bit` `trueOp` `trueInput` ,, olduğu zaman girişi olarak ile işlemini `bit` uygular `true` ve `falseOp(falseInput)` ne zaman geçerlidir `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="bae58-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="bae58-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="bae58-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="bae58-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bae58-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bae58-110">`trueOp`Veya uygulanıp uygulanmadığını belirlemede kullanılan Boolean değeri `falseOp` .</span><span class="sxs-lookup"><span data-stu-id="bae58-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit"></a><span data-ttu-id="bae58-111">trueOp: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bae58-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bae58-112">Ne zaman uygulanacak işlem `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="bae58-112">The operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="bae58-113">Trueınput: 'T</span><span class="sxs-lookup"><span data-stu-id="bae58-113">trueInput : 'T</span></span>

<span data-ttu-id="bae58-114">Olduğunda olarak sağlanacak giriş `trueOp` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="bae58-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit"></a><span data-ttu-id="bae58-115">Yanlışop: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bae58-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bae58-116">Ne zaman uygulanacak işlem `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="bae58-116">The operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="bae58-117">Yanlışgiriş: ' U</span><span class="sxs-lookup"><span data-stu-id="bae58-117">falseInput : 'U</span></span>

<span data-ttu-id="bae58-118">Olduğunda olarak sağlanacak giriş `falseOp` `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="bae58-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bae58-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bae58-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bae58-120">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="bae58-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bae58-121">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="bae58-121">'T</span></span>

<span data-ttu-id="bae58-122">Koşullu olarak uygulanacak işlemin giriş türü `trueOp` .</span><span class="sxs-lookup"><span data-stu-id="bae58-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="bae58-123">' U</span><span class="sxs-lookup"><span data-stu-id="bae58-123">'U</span></span>

<span data-ttu-id="bae58-124">Koşullu olarak uygulanacak işlemin giriş türü `falseOp` .</span><span class="sxs-lookup"><span data-stu-id="bae58-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bae58-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bae58-125">See Also</span></span>

- [<span data-ttu-id="bae58-126">Microsoft. hisse. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="bae58-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="bae58-127">Microsoft. hisse. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="bae58-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="bae58-128">Microsoft. hisse. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="bae58-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="bae58-129">Microsoft. hisse. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="bae58-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="bae58-130">Microsoft. hisse. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="bae58-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)