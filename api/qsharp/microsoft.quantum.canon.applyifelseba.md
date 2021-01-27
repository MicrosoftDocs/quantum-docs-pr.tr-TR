---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: ApplyIfElseBA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: a85567a49df1f261b95f3553da8dc789ce924e7a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844977"
---
# <a name="applyifelseba-operation"></a><span data-ttu-id="1efff-102">ApplyIfElseBA işlemi</span><span class="sxs-lookup"><span data-stu-id="1efff-102">ApplyIfElseBA operation</span></span>

<span data-ttu-id="1efff-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1efff-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1efff-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1efff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1efff-105">Klasik bir bit değerine bağlı olarak iki adjointable işlemden birini uygular.</span><span class="sxs-lookup"><span data-stu-id="1efff-105">Applies one of two adjointable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="1efff-106">Description</span><span class="sxs-lookup"><span data-stu-id="1efff-106">Description</span></span>

<span data-ttu-id="1efff-107">Bir bit verildiğinde, `bit` `trueOp` `trueInput` ,, olduğu zaman girişi olarak ile işlemini `bit` uygular `true` ve `falseOp(falseInput)` ne zaman geçerlidir `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="1efff-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="1efff-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="1efff-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="1efff-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1efff-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1efff-110">`trueOp`Veya uygulanıp uygulanmadığını belirlemede kullanılan Boolean değeri `falseOp` .</span><span class="sxs-lookup"><span data-stu-id="1efff-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-adj"></a><span data-ttu-id="1efff-111">trueOp: 'T => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="1efff-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1efff-112">Olduğunda uygulanacak adjointable işlemi `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="1efff-112">The adjointable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="1efff-113">Trueınput: 'T</span><span class="sxs-lookup"><span data-stu-id="1efff-113">trueInput : 'T</span></span>

<span data-ttu-id="1efff-114">Olduğunda olarak sağlanacak giriş `trueOp` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="1efff-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-adj"></a><span data-ttu-id="1efff-115">Yanlışop: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="1efff-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1efff-116">Olduğunda uygulanacak adjointable işlemi `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="1efff-116">The adjointable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="1efff-117">Yanlışgiriş: ' U</span><span class="sxs-lookup"><span data-stu-id="1efff-117">falseInput : 'U</span></span>

<span data-ttu-id="1efff-118">Olduğunda olarak sağlanacak giriş `falseOp` `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="1efff-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1efff-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1efff-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1efff-120">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="1efff-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1efff-121">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="1efff-121">'T</span></span>

<span data-ttu-id="1efff-122">Koşullu olarak uygulanacak işlemin giriş türü `trueOp` .</span><span class="sxs-lookup"><span data-stu-id="1efff-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="1efff-123">' U</span><span class="sxs-lookup"><span data-stu-id="1efff-123">'U</span></span>

<span data-ttu-id="1efff-124">Koşullu olarak uygulanacak işlemin giriş türü `falseOp` .</span><span class="sxs-lookup"><span data-stu-id="1efff-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1efff-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1efff-125">See Also</span></span>

- [<span data-ttu-id="1efff-126">Microsoft. hisse. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="1efff-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="1efff-127">Microsoft. hisse. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="1efff-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="1efff-128">Microsoft. hisse. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="1efff-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="1efff-129">Microsoft. hisse. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="1efff-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="1efff-130">Microsoft. hisse. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="1efff-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)