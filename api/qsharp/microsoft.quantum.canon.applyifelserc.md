---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: ApplyIfElseRC işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: bac763168dbc7379691f850a79cbb6e61639ba89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841785"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="222f5-102">ApplyIfElseRC işlemi</span><span class="sxs-lookup"><span data-stu-id="222f5-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="222f5-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="222f5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="222f5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="222f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="222f5-105">Klasik sonucun değerine bağlı olarak, iki denetlenebilir işlemden birini uygular.</span><span class="sxs-lookup"><span data-stu-id="222f5-105">Applies one of two controllable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="222f5-106">Description</span><span class="sxs-lookup"><span data-stu-id="222f5-106">Description</span></span>

<span data-ttu-id="222f5-107">Sonuç verildiğinde `result` , `zeroOp` `zeroInput` öğesine eşit olduğu zaman girişi olarak ile işlemi uygular `result` `Zero` ve `oneOp(oneInput)` ne zaman geçerlidir `result == One` .</span><span class="sxs-lookup"><span data-stu-id="222f5-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="222f5-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="222f5-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="222f5-109">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="222f5-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="222f5-110">Ölçüm sonucu, veya uygulanmış olup olmadığını tespit etmek için kullanılır `zeroOp` `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="222f5-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-ctl"></a><span data-ttu-id="222f5-111">Sıfırlama Işleci: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="222f5-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="222f5-112">Ne zaman uygulanacak denetlenebilir işlem `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="222f5-112">The controllable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="222f5-113">Sıfırlama girişi: 'T</span><span class="sxs-lookup"><span data-stu-id="222f5-113">zeroInput : 'T</span></span>

<span data-ttu-id="222f5-114">`zeroOp`Ne zaman sağlanacak giriş `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="222f5-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-ctl"></a><span data-ttu-id="222f5-115">oneOp: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="222f5-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="222f5-116">Ne zaman uygulanacak denetlenebilir işlem `result == One` .</span><span class="sxs-lookup"><span data-stu-id="222f5-116">The controllable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="222f5-117">Oneınput: ' U</span><span class="sxs-lookup"><span data-stu-id="222f5-117">oneInput : 'U</span></span>

<span data-ttu-id="222f5-118">`oneOp`Ne zaman sağlanacak giriş `result == One` .</span><span class="sxs-lookup"><span data-stu-id="222f5-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="222f5-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="222f5-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="222f5-120">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="222f5-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="222f5-121">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="222f5-121">'T</span></span>

<span data-ttu-id="222f5-122">Koşullu olarak uygulanacak işlemin giriş türü `zeroOp` .</span><span class="sxs-lookup"><span data-stu-id="222f5-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="222f5-123">' U</span><span class="sxs-lookup"><span data-stu-id="222f5-123">'U</span></span>

<span data-ttu-id="222f5-124">Koşullu olarak uygulanacak işlemin giriş türü `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="222f5-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="222f5-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="222f5-125">See Also</span></span>

- [<span data-ttu-id="222f5-126">Microsoft. hisse. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="222f5-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="222f5-127">Microsoft. hisse. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="222f5-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="222f5-128">Microsoft. hisse. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="222f5-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="222f5-129">Microsoft. hisse. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="222f5-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="222f5-130">Microsoft. hisse. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="222f5-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)