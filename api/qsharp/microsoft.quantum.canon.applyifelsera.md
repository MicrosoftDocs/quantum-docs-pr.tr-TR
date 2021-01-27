---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: ApplyIfElseRA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: 0a7683adfa15f787f96c7ae55f94e2c52426df75
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845024"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="71607-102">ApplyIfElseRA işlemi</span><span class="sxs-lookup"><span data-stu-id="71607-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="71607-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="71607-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="71607-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71607-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71607-105">Klasik sonucun değerine bağlı olarak iki adjointable işlemlerinden birini uygular.</span><span class="sxs-lookup"><span data-stu-id="71607-105">Applies one of two adjointable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="71607-106">Description</span><span class="sxs-lookup"><span data-stu-id="71607-106">Description</span></span>

<span data-ttu-id="71607-107">Sonuç verildiğinde `result` , `zeroOp` `zeroInput` öğesine eşit olduğu zaman girişi olarak ile işlemi uygular `result` `Zero` ve `oneOp(oneInput)` ne zaman geçerlidir `result == One` .</span><span class="sxs-lookup"><span data-stu-id="71607-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="71607-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="71607-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="71607-109">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="71607-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="71607-110">Ölçüm sonucu, veya uygulanmış olup olmadığını tespit etmek için kullanılır `zeroOp` `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="71607-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-adj"></a><span data-ttu-id="71607-111">Sıfırlama işlemi: 'T => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="71607-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="71607-112">Ne zaman uygulanacak adjointable işlemi `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="71607-112">The adjointable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="71607-113">Sıfırlama girişi: 'T</span><span class="sxs-lookup"><span data-stu-id="71607-113">zeroInput : 'T</span></span>

<span data-ttu-id="71607-114">`zeroOp`Ne zaman sağlanacak giriş `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="71607-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-adj"></a><span data-ttu-id="71607-115">oneOp: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="71607-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="71607-116">Ne zaman uygulanacak adjointable işlemi `result == One` .</span><span class="sxs-lookup"><span data-stu-id="71607-116">The adjointable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="71607-117">Oneınput: ' U</span><span class="sxs-lookup"><span data-stu-id="71607-117">oneInput : 'U</span></span>

<span data-ttu-id="71607-118">`oneOp`Ne zaman sağlanacak giriş `result == One` .</span><span class="sxs-lookup"><span data-stu-id="71607-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71607-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71607-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="71607-120">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="71607-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71607-121">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="71607-121">'T</span></span>

<span data-ttu-id="71607-122">Koşullu olarak uygulanacak işlemin giriş türü `zeroOp` .</span><span class="sxs-lookup"><span data-stu-id="71607-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="71607-123">' U</span><span class="sxs-lookup"><span data-stu-id="71607-123">'U</span></span>

<span data-ttu-id="71607-124">Koşullu olarak uygulanacak işlemin giriş türü `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="71607-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="71607-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="71607-125">See Also</span></span>

- [<span data-ttu-id="71607-126">Microsoft. hisse. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="71607-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="71607-127">Microsoft. hisse. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="71607-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="71607-128">Microsoft. hisse. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="71607-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="71607-129">Microsoft. hisse. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="71607-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="71607-130">Microsoft. hisse. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="71607-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)