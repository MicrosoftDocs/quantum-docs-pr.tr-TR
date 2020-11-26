---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: ApplyIfElseR işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 874dae2ba5e842066e9c1582af431a73520e4ccd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209545"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="f55ad-102">ApplyIfElseR işlemi</span><span class="sxs-lookup"><span data-stu-id="f55ad-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="f55ad-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f55ad-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f55ad-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f55ad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f55ad-105">Klasik sonucun değerine bağlı olarak iki işlemden birini uygular.</span><span class="sxs-lookup"><span data-stu-id="f55ad-105">Applies one of two operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="f55ad-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f55ad-106">Description</span></span>

<span data-ttu-id="f55ad-107">Sonuç verildiğinde `result` , `zeroOp` `zeroInput` öğesine eşit olduğu zaman girişi olarak ile işlemi uygular `result` `Zero` ve `oneOp(oneInput)` ne zaman geçerlidir `result == One` .</span><span class="sxs-lookup"><span data-stu-id="f55ad-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="f55ad-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="f55ad-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="f55ad-109">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="f55ad-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="f55ad-110">Ölçüm sonucu, veya uygulanmış olup olmadığını tespit etmek için kullanılır `zeroOp` `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="f55ad-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit"></a><span data-ttu-id="f55ad-111">Sıfırlama Işleci: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f55ad-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f55ad-112">Ne zaman uygulanacak işlem `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="f55ad-112">The operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="f55ad-113">Sıfırlama girişi: 'T</span><span class="sxs-lookup"><span data-stu-id="f55ad-113">zeroInput : 'T</span></span>

<span data-ttu-id="f55ad-114">`zeroOp`Ne zaman sağlanacak giriş `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="f55ad-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit"></a><span data-ttu-id="f55ad-115">oneOp: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f55ad-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f55ad-116">Ne zaman uygulanacak işlem `result == One` .</span><span class="sxs-lookup"><span data-stu-id="f55ad-116">The operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="f55ad-117">Oneınput: ' U</span><span class="sxs-lookup"><span data-stu-id="f55ad-117">oneInput : 'U</span></span>

<span data-ttu-id="f55ad-118">`oneOp`Ne zaman sağlanacak giriş `result == One` .</span><span class="sxs-lookup"><span data-stu-id="f55ad-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f55ad-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f55ad-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f55ad-120">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f55ad-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f55ad-121">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f55ad-121">'T</span></span>

<span data-ttu-id="f55ad-122">Koşullu olarak uygulanacak işlemin giriş türü `zeroOp` .</span><span class="sxs-lookup"><span data-stu-id="f55ad-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="f55ad-123">' U</span><span class="sxs-lookup"><span data-stu-id="f55ad-123">'U</span></span>

<span data-ttu-id="f55ad-124">Koşullu olarak uygulanacak işlemin giriş türü `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="f55ad-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f55ad-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f55ad-125">See Also</span></span>

- [<span data-ttu-id="f55ad-126">Microsoft. hisse. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="f55ad-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="f55ad-127">Microsoft. hisse. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="f55ad-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="f55ad-128">Microsoft. hisse. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="f55ad-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="f55ad-129">Microsoft. hisse. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="f55ad-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="f55ad-130">Microsoft. hisse. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="f55ad-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)