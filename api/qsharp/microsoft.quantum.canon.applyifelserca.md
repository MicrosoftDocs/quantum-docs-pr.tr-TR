---
uid: Microsoft.Quantum.Canon.ApplyIfElseRCA
title: ApplyIfElseRCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical result.
ms.openlocfilehash: dfd1c16a25a2da507024813a380386c8f4e49d30
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218759"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="2520b-102">ApplyIfElseRCA işlemi</span><span class="sxs-lookup"><span data-stu-id="2520b-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="2520b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2520b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2520b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2520b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2520b-105">Klasik sonucun değerine bağlı olarak iki Unitary işlemden birini uygular.</span><span class="sxs-lookup"><span data-stu-id="2520b-105">Applies one of two unitary operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRCA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj + Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Adj + Ctl), oneInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2520b-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2520b-106">Description</span></span>

<span data-ttu-id="2520b-107">Sonuç verildiğinde `result` , `zeroOp` `zeroInput` öğesine eşit olduğu zaman girişi olarak ile işlemi uygular `result` `Zero` ve `oneOp(oneInput)` ne zaman geçerlidir `result == One` .</span><span class="sxs-lookup"><span data-stu-id="2520b-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="2520b-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="2520b-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="2520b-109">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="2520b-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="2520b-110">Ölçüm sonucu, veya uygulanmış olup olmadığını tespit etmek için kullanılır `zeroOp` `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="2520b-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="2520b-111">Sıfırlama: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="2520b-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2520b-112">Ne zaman uygulanacak Unitary işlemi `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="2520b-112">The unitary operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="2520b-113">Sıfırlama girişi: 'T</span><span class="sxs-lookup"><span data-stu-id="2520b-113">zeroInput : 'T</span></span>

<span data-ttu-id="2520b-114">`zeroOp`Ne zaman sağlanacak giriş `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="2520b-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-adj--ctl"></a><span data-ttu-id="2520b-115">oneOp: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="2520b-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2520b-116">Ne zaman uygulanacak Unitary işlemi `result == One` .</span><span class="sxs-lookup"><span data-stu-id="2520b-116">The unitary operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="2520b-117">Oneınput: ' U</span><span class="sxs-lookup"><span data-stu-id="2520b-117">oneInput : 'U</span></span>

<span data-ttu-id="2520b-118">`oneOp`Ne zaman sağlanacak giriş `result == One` .</span><span class="sxs-lookup"><span data-stu-id="2520b-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2520b-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2520b-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2520b-120">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2520b-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2520b-121">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="2520b-121">'T</span></span>

<span data-ttu-id="2520b-122">Koşullu olarak uygulanacak işlemin giriş türü `zeroOp` .</span><span class="sxs-lookup"><span data-stu-id="2520b-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="2520b-123">' U</span><span class="sxs-lookup"><span data-stu-id="2520b-123">'U</span></span>

<span data-ttu-id="2520b-124">Koşullu olarak uygulanacak işlemin giriş türü `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="2520b-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2520b-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2520b-125">See Also</span></span>

- [<span data-ttu-id="2520b-126">Microsoft. hisse. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="2520b-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="2520b-127">Microsoft. hisse. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="2520b-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="2520b-128">Microsoft. hisse. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="2520b-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="2520b-129">Microsoft. hisse. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="2520b-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="2520b-130">Microsoft. hisse. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="2520b-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)