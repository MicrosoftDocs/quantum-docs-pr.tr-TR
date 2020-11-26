---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 35be5425fcd76eae9e0a6fde6a689a5db00da52f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204598"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="ed83b-102">UncurriedOpC işlevi</span><span class="sxs-lookup"><span data-stu-id="ed83b-102">UncurriedOpC function</span></span>

<span data-ttu-id="ed83b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ed83b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ed83b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed83b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ed83b-105">İşlemleri döndüren bir işlev verildiğinde, her iki girişi de tanımlama grubu olarak alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="ed83b-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="ed83b-106">Değiştirici, `C` işlemlerin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="ed83b-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="ed83b-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="ed83b-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="ed83b-108">curriedOp: 'T-> ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="ed83b-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="ed83b-109">İşlemleri döndüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="ed83b-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="ed83b-110">Çıkış: ('T, ' U) => [birimi](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="ed83b-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="ed83b-111">`op`İle eşdeğer olan yeni bir işlem `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="ed83b-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ed83b-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ed83b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ed83b-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ed83b-113">'T</span></span>

<span data-ttu-id="ed83b-114">Bir curried işlevinin ilk bağımsız değişkeninin türü.</span><span class="sxs-lookup"><span data-stu-id="ed83b-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="ed83b-115">' U</span><span class="sxs-lookup"><span data-stu-id="ed83b-115">'U</span></span>

<span data-ttu-id="ed83b-116">Bir curried işlevinin ikinci bağımsız değişkeninin türü.</span><span class="sxs-lookup"><span data-stu-id="ed83b-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed83b-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ed83b-117">See Also</span></span>

- [<span data-ttu-id="ed83b-118">Microsoft. hisse. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="ed83b-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)