---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728291"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="4dbed-102">UncurriedOpC işlevi</span><span class="sxs-lookup"><span data-stu-id="4dbed-102">UncurriedOpC function</span></span>

<span data-ttu-id="4dbed-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4dbed-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4dbed-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4dbed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4dbed-105">İşlemleri döndüren bir işlev verildiğinde, her iki girişi de tanımlama grubu olarak alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="4dbed-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="4dbed-106">Değiştirici, `C` işlemlerin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="4dbed-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="4dbed-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="4dbed-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl"></a><span data-ttu-id="4dbed-108">curriedOp: 'T-> ' U => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="4dbed-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="4dbed-109">İşlemleri döndüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="4dbed-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl"></a><span data-ttu-id="4dbed-110">Çıkış: ('T, ' U) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="4dbed-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="4dbed-111">`op`İle eşdeğer olan yeni bir işlem `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="4dbed-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4dbed-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="4dbed-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4dbed-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="4dbed-113">'T</span></span>

<span data-ttu-id="4dbed-114">Bir curried işlevinin ilk bağımsız değişkeninin türü.</span><span class="sxs-lookup"><span data-stu-id="4dbed-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="4dbed-115">' U</span><span class="sxs-lookup"><span data-stu-id="4dbed-115">'U</span></span>

<span data-ttu-id="4dbed-116">Bir curried işlevinin ikinci bağımsız değişkeninin türü.</span><span class="sxs-lookup"><span data-stu-id="4dbed-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="4dbed-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4dbed-117">See Also</span></span>

- [<span data-ttu-id="4dbed-118">Microsoft. hisse. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="4dbed-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)