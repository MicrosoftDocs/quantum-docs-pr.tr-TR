---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: f811347d65a6460690163e9df631979c906bd89f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840777"
---
# <a name="curriedop-function"></a><span data-ttu-id="33502-102">CurriedOp işlevi</span><span class="sxs-lookup"><span data-stu-id="33502-102">CurriedOp function</span></span>

<span data-ttu-id="33502-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="33502-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="33502-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="33502-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="33502-105">İki giriş üzerinde bir işlemin curried sürümünü döndürür.</span><span class="sxs-lookup"><span data-stu-id="33502-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="33502-106">Diğer bir deyişle, iki girişli bir işlem söz konusu olduğunda, bu işlev bir girişin bir işlemini döndüren tek bir girdinin işlemini döndürmek için Curry 'nin isomorphism $f (x, y) \equf (x) (y) $ ' u uygular.</span><span class="sxs-lookup"><span data-stu-id="33502-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="33502-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="33502-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="33502-108">Op: ('T, ' U) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33502-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="33502-109">Girdisi bir çift olan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="33502-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="33502-110">Çıkış: 'T-> ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33502-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="33502-111">Bir çiftin ilk öğesini kabul eden ve özgün işlem girişinin ikinci öğesini girdi olarak kabul eden bir işlem döndüren bir işlem.</span><span class="sxs-lookup"><span data-stu-id="33502-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="33502-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="33502-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="33502-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="33502-113">'T</span></span>

<span data-ttu-id="33502-114">Çiftler üzerinde tanımlanan bir işlevin ilk bileşen türü.</span><span class="sxs-lookup"><span data-stu-id="33502-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="33502-115">' U</span><span class="sxs-lookup"><span data-stu-id="33502-115">'U</span></span>

<span data-ttu-id="33502-116">Çiftler üzerinde tanımlanan bir işlevin ikinci bileşen türü.</span><span class="sxs-lookup"><span data-stu-id="33502-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="33502-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="33502-117">Remarks</span></span>

<span data-ttu-id="33502-118">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="33502-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```