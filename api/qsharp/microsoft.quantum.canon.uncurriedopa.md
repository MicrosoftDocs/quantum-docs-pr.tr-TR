---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: e535d017d2665ddb76e5f422e18b8656c73171c6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204632"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="eac73-102">UncurriedOpA işlevi</span><span class="sxs-lookup"><span data-stu-id="eac73-102">UncurriedOpA function</span></span>

<span data-ttu-id="eac73-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eac73-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eac73-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eac73-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eac73-105">İşlemleri döndüren bir işlev verildiğinde, her iki girişi de tanımlama grubu olarak alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="eac73-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="eac73-106">Değiştirici, `A` işlemlerin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="eac73-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="eac73-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="eac73-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="eac73-108">curriedOp: 'T-> ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="eac73-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="eac73-109">İşlemleri döndüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="eac73-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj"></a><span data-ttu-id="eac73-110">Çıkış: ('T, ' U) => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="eac73-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="eac73-111">`op`İle eşdeğer olan yeni bir işlem `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="eac73-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="eac73-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="eac73-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eac73-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="eac73-113">'T</span></span>

<span data-ttu-id="eac73-114">Bir curried işlevinin ilk bağımsız değişkeninin türü.</span><span class="sxs-lookup"><span data-stu-id="eac73-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="eac73-115">' U</span><span class="sxs-lookup"><span data-stu-id="eac73-115">'U</span></span>

<span data-ttu-id="eac73-116">Bir curried işlevinin ikinci bağımsız değişkeninin türü.</span><span class="sxs-lookup"><span data-stu-id="eac73-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="eac73-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="eac73-117">See Also</span></span>

- [<span data-ttu-id="eac73-118">Microsoft. hisse. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="eac73-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)