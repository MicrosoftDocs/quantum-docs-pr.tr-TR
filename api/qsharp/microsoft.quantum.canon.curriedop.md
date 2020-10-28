---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 13bc3e195d8a4ba26b726f96e4dc6b83da43c3e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728784"
---
# <a name="curriedop-function"></a><span data-ttu-id="ed0cb-102">CurriedOp işlevi</span><span class="sxs-lookup"><span data-stu-id="ed0cb-102">CurriedOp function</span></span>

<span data-ttu-id="ed0cb-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ed0cb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ed0cb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed0cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed0cb-105">İki giriş üzerinde bir işlemin curried sürümünü döndürür.</span><span class="sxs-lookup"><span data-stu-id="ed0cb-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="ed0cb-106">Diğer bir deyişle, iki girişli bir işlem söz konusu olduğunda, bu işlev bir girişin bir işlemini döndüren tek bir girdinin işlemini döndürmek için Curry 'nin isomorphism $f (x, y) \equf (x) (y) $ ' u uygular.</span><span class="sxs-lookup"><span data-stu-id="ed0cb-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="ed0cb-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="ed0cb-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="ed0cb-108">Op: ('T, ' U) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ed0cb-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ed0cb-109">Girdisi bir çift olan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="ed0cb-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="ed0cb-110">Çıkış: 'T-> ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ed0cb-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ed0cb-111">Bir çiftin ilk öğesini kabul eden ve özgün işlem girişinin ikinci öğesini girdi olarak kabul eden bir işlem döndüren bir işlem.</span><span class="sxs-lookup"><span data-stu-id="ed0cb-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ed0cb-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ed0cb-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ed0cb-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ed0cb-113">'T</span></span>

<span data-ttu-id="ed0cb-114">Çiftler üzerinde tanımlanan bir işlevin ilk bileşen türü.</span><span class="sxs-lookup"><span data-stu-id="ed0cb-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="ed0cb-115">' U</span><span class="sxs-lookup"><span data-stu-id="ed0cb-115">'U</span></span>

<span data-ttu-id="ed0cb-116">Çiftler üzerinde tanımlanan bir işlevin ikinci bileşen türü.</span><span class="sxs-lookup"><span data-stu-id="ed0cb-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed0cb-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ed0cb-117">Remarks</span></span>

<span data-ttu-id="ed0cb-118">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="ed0cb-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```