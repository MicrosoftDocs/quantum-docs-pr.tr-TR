---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728292"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="3eba4-102">UncurriedOpA işlevi</span><span class="sxs-lookup"><span data-stu-id="3eba4-102">UncurriedOpA function</span></span>

<span data-ttu-id="3eba4-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3eba4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3eba4-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3eba4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3eba4-105">İşlemleri döndüren bir işlev verildiğinde, her iki girişi de tanımlama grubu olarak alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="3eba4-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="3eba4-106">Değiştirici, `A` işlemlerin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="3eba4-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="3eba4-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="3eba4-107">Input</span></span>

### <a name="curriedop--t---u--unit-adj"></a><span data-ttu-id="3eba4-108">curriedOp: 'T-> ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="3eba4-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="3eba4-109">İşlemleri döndüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="3eba4-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-adj"></a><span data-ttu-id="3eba4-110">Çıkış: ('T, ' U) => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="3eba4-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="3eba4-111">`op`İle eşdeğer olan yeni bir işlem `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="3eba4-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3eba4-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="3eba4-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3eba4-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="3eba4-113">'T</span></span>

<span data-ttu-id="3eba4-114">Bir curried işlevinin ilk bağımsız değişkeninin türü.</span><span class="sxs-lookup"><span data-stu-id="3eba4-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="3eba4-115">' U</span><span class="sxs-lookup"><span data-stu-id="3eba4-115">'U</span></span>

<span data-ttu-id="3eba4-116">Bir curried işlevinin ikinci bağımsız değişkeninin türü.</span><span class="sxs-lookup"><span data-stu-id="3eba4-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="3eba4-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3eba4-117">See Also</span></span>

- [<span data-ttu-id="3eba4-118">Microsoft. hisse. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="3eba4-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)